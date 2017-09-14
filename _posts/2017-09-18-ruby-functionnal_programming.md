---
date: '2017-09-14T03:10:00.001-0700'
tags: ruby functionnal
---

see
https://medium.com/craft-academy/functional-programming-in-ruby-for-people-who-dont-know-what-functional-programming-is-f0c4ab7dc68c



What is functional programming?

As a Rubyist, I’m used to talking about objects. We instantiate them, then call methods on them. We pass them, we manipulate them. In object-oriented programming (OOP), everything is an object. In functional programming, we organize our code around functions.
Pure

It’s hard to get too far into talking about functional programming without discussing the concept of “pure”. A function is pure if it a) always produces the same output from a given input and b) has no side effects. We’ll look at both of those in greater detail.
First-Class and Higher-Order Functions

A higher-order function is one that can take a function or return one as an argument. When a language can handle those actions, we say that it has first-class function support. (They sound like opposite things but mean the same thing? Yeah, basically.) Here’s a quick example:

{% highlight ruby %}
add = lambda { |x,y| x + y }
sub = lambda { |x,y| x - y }

def math(method, x, y)
 method.call(x,y) * 2
end
{% endhighlight %}

We’ll get into lambdas after the discussion on theory, but for now you can just think of them as methods. What I have above is really not so different from this, except that Ruby won’t let you write it:

{% highlight ruby %}
def add(x,y)
  x + y
end

def math(method, x, y)
 method(x,y) * 2
end
{% endhighlight %}

You can go ahead and try to call math(add(1,2)) and get a ton of errors. Instead we have to store methods inside of lambdas so they can be passed around through other methods (as in my first example of this code).

When we call math, we are asking for a method to be passed that will execute according to its own rules. The math method will take a higher-order function as an input. In Ruby, those higher-order functions need to be lambdas (or procs).

When we call this:

{% highlight ruby %}
2.3.0 :032 > math(add, 1, 2)
=> 6
{% endhighlight %}

Note that we are concerned with the output of the math method and that the add method (lambda) has not changed at all. Likewise, x and y are also unchanged. It doesn’t matter how many times we run this method, we will always get the same output given the same input add, 1, 2. It is pure.
State Changes & Side Effects

Functional programming requires that no states are changed when a function is run — we simply use the output of those functions. These are also referred to as side effects. Here’s an example:

In Ruby, if we have an account with a balance, we might want to augment that balance:

{% highlight ruby %}
class Account
  attr_accessor :balance

  def initialize
    @balance = 100
  end

  def deposit(amount)
    balance += amount
  end
end
{% endhighlight %}

Instances of the Account class — that is, objects — will be able to perform the deposit method. That will change the state of the object on which the method is being performed:

{% highlight ruby %}
> account = Account.new
> account.balance
=> 100
> account.deposit(50)
=> 150
> account.balance
=> 150 
{% endhighlight %}

The balance attribute has been affected by the deposit method. It’s state has changed from 100 to 150.

Note that if we run this method again with the same input, we get a different output. It is not pure.

Compare this result with the functional math example above. Here our states are changing. In the previous example, x and y are unchanged between iterations of the function.

Side effects are literally anything a function does to the rest of the program, aside from taking in input and producing output. A console log is a side effect. Calling a function which produces side effects is a side effect. Functional programming is concerned with creating an entirely safe space in which functions can operate.
A Few More Concepts

    Referential transparency: The ability to replace a function call with its resulting value. In our math example, that would mean we could replace math(add, 1, 2) with 6 without breaking anything. Pure functions are always referentially transparent.
    Function composition: Combining two or more functions at once. We already saw this, with math(add, 1, 2) — we combined the math and add functions.

Why would anyone want to do this?

Functional programming allows for far fewer bugs. With states remaining constant, you would never find your deposit method suddenly messing with your withdraw method: the two don’t affect each other unless they interact directly.

Functional programming is also far less interested in the order in which methods are called, as each method lives in its own “pure” bubble. With object-oriented programming, we must first create the object (say instantiate an Account), then perhaps give it a balance and then call withdraw. The order in which the functions are called matters.

And since I haven’t done any amount of functional programming, I’ll just trust the internets that functional programming is easy to test, but is also slower than other programming paradigms.
Can you combine programming paradigms?

Yes.

The internets suggest you keep your pure functions isolated from your state-dependent functions in order to preserve the greatest purity in your program.
Functional Programming in Ruby

If you have been writing even a little Ruby code, you have already used some functional programming technique. The .each method, for instance, uses a Proc. See this link for a thorough description of what is actually going on under the hood of the .each method.
Lambdas

Above, I defined the add and sub lambdas:

{% highlight ruby %}
add = lambda { |x,y| x + y }
sub = lambda { |x,y| x - y }
{% endhighlight %}

They can also be written with this shorthand:

{% highlight ruby %}
add = -> (x,y) { x + y }
sub = -> (x,y) { x - y }
{% endhighlight %}

Here we are storing a function inside of a variable. We are not storing the output of a function, but rather the entire function itself. We can now call this function from within another method, as we did above:

{% highlight ruby %}
2.3.0 :032 > math(add, 1, 2)
=> 6
{% endhighlight %}

A lambda behaves just like a method, but is defined in such a way that it can be passed to another method. It requires arguments if its definition requires arguments.
Procs

Lambdas are actually procs with more rules. A Proc is a block — a series of commands that can be executed. A lambda, on the other hand, is a block plus a method definition. A lambda throws method-type errors but a proc only throws block errors:

{% highlight ruby %}
add = lambda { |x,y| x + y }
proc = Proc.new { |x, y| x + y }

2.3.0 :010 > add.call(1,2)
=> 3

2.3.0 :011 > add.call
ArgumentError: wrong number of arguments (given 0, expected 2)

2.3.0 :012 > proc.call(1,2)
=> 3

2.3.0 :013 > proc.call
NoMethodError: undefined method `+' for nil:NilClass
{% endhighlight %}

The proc tries to run and doesn’t throw an error at the call, but rather inside the function block itself (trying to add nil to nil). The lambda throws the error at the method call itself, recognizing that no arguments have been passed.
Return statements

The other difference between procs and lambdas is how they handle return statements. In short, lambdas return to their containing method (the method from which they were called). Procs return from their containing method as well, but since they are blocks and not methods, they will end the entire process they are inside. Again, Philip Brown has done a great job of illustrating this with examples, so I’ll just point you there.


