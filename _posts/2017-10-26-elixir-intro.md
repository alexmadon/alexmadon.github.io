---
date: '2017-10-26T03:10:00.001-0700'
tags: linux erlang elixir
---

# Elixir Introduction


## Declarative Programming 12

No 'for' loop. For loop is imperative as it desccribes how to loop (e.g on a list).

```elixir
numbers=[1,-1,2,-4,5,-9]
Enum.filter(numbers, fn u -> u>=0 end)
```

gives:mv 


```elixir
iex(4)> numbers=[1,-1,2,-4,5,-9]
[1, -1, 2, -4, 5, -9]
iex(5)> Enum.filter(numbers, fn u -> u>=0 end)
[1, 2, 5]
```


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


Examples from https://www.youtube.com/watch?v=wVrnoxNbOts