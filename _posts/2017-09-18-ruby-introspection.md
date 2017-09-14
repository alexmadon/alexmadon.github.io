---
date: '2017-09-14T03:10:00.001-0700'
tags: ruby introspection
---

see https://www.leighhalliday.com/ruby-introspection-metaprogramming


What is introspection?

Introspection in general terms means to look inward. Humans can perform introspection, maybe questioning why we made a certain decision or finding out what makes us happy, and Ruby too can perform introspection.

In Ruby, introspection is when our code asks questions about itself. Maybe that sounds weird... so let's move on to some examples!
Introspecting our Ruby code

The following examples will be looking at this small piece of code below which defines an Alpaca class, which has a couple instance variables and a method:

{% highlight ruby %}
class Alpaca

  attr_accessor :name, :birthdate

  def initialize(name, birthdate)
    @name      = name
    @birthdate = birthdate
  end

  def spit
    "Putsuuey"
  end

end
{% endhighlight %}

All objects in Ruby extend from Object

In Ruby you are able to create subclasses of core classes or classes that you create yourself. When you do this, you're saying that the class you are creating is like, but is a more specialized version of the parent it extends from.

{% highlight ruby %}
class Alpaca < Camelid
end
{% endhighlight %}

We're saying here that Alpaca is like a Camelid, and inherits any properties or methods that a Camelid has, but also has it's own more specific properties, and may have to modify slightly the behaviour of a more generic Camelid.

Well, in Ruby, all classes eventually extend (even though you don't have to explicitly tell it to do so) from the base class of Object. Object provides many useful methods for introspection!
I just want to see what data I am working with!

Luckily, Ruby has a pretty good solution for this and it is the inspect method. This method converts the object you are working with into a human-readable form. It's very useful for debugging and when you're not sure what data you are working with.

{% highlight ruby %}
puts spitty.inspect
#<Alpaca:0x007fd849166808 @name="Spitty", @birthdate=#<Date: 1984-11-11 ((2446016j,0s,0n),+0s,2299161j)>>
{% endhighlight %}

This tells us that spitty is an instance of the Alpaca class and that it has 2 instance variables (@name and @birthdate).
What type of class is this?

When you want to know what type of class/object you're working with, you can use the class method. The object it returns has a name method which will return a string representation of the class.

{% highlight ruby %}
puts spitty.class.name
# Alpaca
{% endhighlight %}

If you want to check to see if this object is an instance of a specific class, you can use the instance_of? method, which will return a boolean response.

{% highlight ruby %}
puts spitty.instance_of?(Alpaca)
# true
{% endhighlight %}

What methods are available to me?

To answer this question you can call the methods method, which will return an array of the methods available to the object instance you are working with. If I were to call it on my Alpaca instance, spitty, most of the methods I see come from it's parent, Object, but I also see the spit method that I defined.

{% highlight ruby %}
puts spitty.methods.inspect
[:name, :name=, :birthdate, :birthdate=, :spit, :nil?, :===, :=~, :!~, :eql?, :hash, :<=>, :class, :singleton_class, :clone, :dup, :taint, :tainted?, :untaint, :untrust, :untrusted?, :trust, :freeze, :frozen?, :to_s, :inspect, :methods, :singleton_methods, :protected_methods, :private_methods, :public_methods, :instance_variables, :instance_variable_get, :instance_variable_set, :instance_variable_defined?, :remove_instance_variable, :instance_of?, :kind_of?, :is_a?, :tap, :send, :public_send, :respond_to?, :extend, :display, :method, :public_method, :singleton_method, :define_singleton_method, :object_id, :to_enum, :enum_for, :==, :equal?, :!, :!=, :instance_eval, :instance_exec, :__send__, :__id__]
{% endhighlight %}

If you'd rather just ask the object instance if it has a specific method, you would use the respond_to? method.

{% highlight ruby %}
puts spitty.respond_to?(:spit)
# true
{% endhighlight %}

Which instance variables are defined?

To find out which instance variables are defined-you know, the ones with the @ before them-you can use the instance_variables method.

{% highlight ruby %}
puts spitty.instance_variables.inspect
[:@name, :@birthdate]
{% endhighlight %}
