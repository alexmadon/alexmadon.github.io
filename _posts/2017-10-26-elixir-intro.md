---
date: '2017-10-26T03:10:00.001-0700'
tags: linux erlang elixir
---


# Elixir Introduction 1
{:.no_toc}

* TOC
{:toc}

## Declarative Programming

No 'for' loop. For loop is imperative as it desccribes how to loop (e.g on a list).

```elixir
numbers=[1,-1,2,-4,5,-9]
Enum.filter(numbers, fn u -> u>=0 end)
```

gives:


```elixir
iex(4)> numbers=[1,-1,2,-4,5,-9]
[1, -1, 2, -4, 5, -9]
iex(5)> Enum.filter(numbers, fn u -> u>=0 end)
[1, 2, 5]
```

## First class functions

Same but using *first class functions*:

```elixir
numbers=[1,-1,2,-4,5,-9]
afilter=fn u -> u>=0 end
Enum.filter(numbers,afilter)
```
that gives:

```elixir
iex(1)> numbers=[1,-1,2,-4,5,-9]
[1, -1, 2, -4, 5, -9]
iex(2)> afilter=fn u -> u>=0 end
#Function<6.50752066/1 in :erl_eval.expr/5>
iex(3)> Enum.filter(numbers,afilter)
[1, 2, 5]
```

## Immutable Data

```elixir
numbers=[1,-1,2,-4,5,-9]
numbers_filtered=Enum.filter(numbers, fn u -> u>=0 end)
numbers
numbers_filtered
```

```elixir
iex(4)> numbers=[1,-1,2,-4,5,-9]
[1, -1, 2, -4, 5, -9]
iex(5)> numbers_filtered=Enum.filter(numbers, fn u -> u>=0 end)
[1, 2, 5]
iex(6)> numbers
[1, -1, 2, -4, 5, -9]
iex(7)> numbers_filtered
[1, 2, 5]
```
The original array 'numbers' is not modified.


## Pipe Operator and first argument as subject in pipes
```elixir
$ iex
Erlang/OTP 18 [erts-7.3] [source] [64-bit] [smp:8:8] [async-threads:10] [kernel-poll:false]

Interactive Elixir (1.1.0-dev) - press Ctrl+C to exit (type h() ENTER for help)
iex(1)> alist=[1,2,3,4,5,6]
[1, 2, 3, 4, 5, 6]
iex(2)> Enum.at(alist,3)
4
iex(3)> alist |>
...(3)> Enum.at(3)
4
```

## Use IO.inspect to debug

```elixir
alist=[[1,2],[3,4],[5,6]]

alist |>
Enum.at(1) |>
Enum.at(0)

alist |>
Enum.at(1) |>
IO.inspect |>
Enum.at(0)
```




```elixir
iex(1)> alist=[[1,2],[3,4],[5,6]]
[[1, 2], [3, 4], [5, 6]]
iex(2)> 
nil
iex(3)> alist |>
...(3)> Enum.at(1) |>
...(3)> Enum.at(0)
3


iex(5)> alist |>
...(5)> Enum.at(1) |>
...(5)> IO.inspect |>
...(5)> Enum.at(0)
[3, 4]
3
```


Examples inspired from https://www.youtube.com/watch?v=wVrnoxNbOts
