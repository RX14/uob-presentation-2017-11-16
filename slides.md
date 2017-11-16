---
author: Chris Hobbs
title: '<img src="crystal_logo.svg" style="border: none; box-shadow: none; width: 85%; height: 85%"/>'
pagetitle: Crystal
date: November 16, 2017
theme: white
---

# What is Crystal?

---

::: notes
- AT START: We're going to go over topics which aren't covered in the first year, bear with me.
- You're all here to know...

Typos
:::

> - Programming Language
>   - Web services
>   - CLI tools
>   - Even kernels!
> - Based on Ruby syntax
>   - It's not Ruby
>   - Keep the programmer happy
>   - At the expense of the compiler
> - Statically typed (safe)
> - Fast!
> - Awesome!
> - Beta status :(

# History

---

::: notes
5 years!

- Recommend open source
  - Learn a lot troubleshooting others
- Find a (medium-size) project you like and press the github watch button
:::

- First commit September 2012
- Got involved Spring 2016
- Core maintainer June 2017

# Motivation

---

> - Originally a project to compile ruby
> - Dynamic languages tradeoff speed for flexibility
> - Compiled languages tradeoff flexibility for speed
> - Static type checking reduces errors
> - But we want the best of all worlds!

# What does it look like?

---

```ruby
puts "Hello World!"
```

---

```ruby
# A very basic HTTP server
require "http/server"

server = HTTP::Server.new(8080) do |context|
  path = context.request.path

  context.response.content_type = "text/plain"
  context.response.print "Hello world, got #{path}!"
end

puts "Listening on http://127.0.0.1:8080"
server.listen
```

## Statically typed

```ruby
array = [1, 2, 3, nil]
array.map { |x| x + 1 }
```
. . .

```
Error in line 2: undefined method '+' for Nil (compile-time type is (Int32 | Nil))
```

## Flexible

```ruby
def add(x)
  x + x
end

puts add(1)
puts add("hi")
```

. . .

```
2
hihi
```

. . .

No type annotations!

## Behind the scenes

```ruby
def add(x : Int32)
def add(x : String)
```

## Cool things I don't have time for

Please ask me later!

- Concurrency (CSP)
- I/O
- Macros
- Community
- Package management
- Portability

# Questions
## Goodbye!

- Check out crystal at https://crystal-lang.org/
- These slides are open source at https://github.com/RX14/uob-presentation-2017-11-16
