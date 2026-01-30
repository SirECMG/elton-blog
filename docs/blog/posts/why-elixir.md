---
  date: 2025-08-10
  draft: true
---

# Why Elixir?
I have been dabbling with Elixir recently and have been enjoying my time with this language.

I am writing a post to explain why I think it is a great language.

## simplicity
It is simple, powerful.

the primitive type system is super small. below is the list of basic types
```elixir
1          # integer
0x1F       # integer
1.0        # float
true       # boolean
:atom      # atom / symbol
"elixir"   # string
[1, 2, 3]  # list
{1, 2, 3}  # tuple
```

## simple module system

```elixir
defmodule Calculator do
  def add(x,y) do
    x + y
  end
end
Calculator.add(1,2)
```

## concise code

it combines deconstruction and pattern matching to produce concise syntax.
```elixir
defmodule UserHandler do
  # Pattern matching in function arguments
  def process_response({:ok, user_data}) do
    %{name: name, email: email} = user_data
    "Welcome #{name}! Email: #{email}"
  end

  def process_response({:error, reason}) do
    "Error occurred: #{reason}"
  end

  def process_response({:timeout}) do
    "Request timed out, please try again"
  end
end


# Usage examples:
UserHandler.process_response({:ok, %{name: "John", email: "john@example.com"}})
# Returns: "Welcome John! Email: john@example.com"

UserHandler.process_response({:error, "User not found"})
# Returns: "Error occurred: User not found"
```
this is idiomatic elixir, it typically uses method overloading with pattern matching and deconstruction

pipe operator

guards

## fast development flow

the development flow is fast. with elixir it is an interpreted language so there is no compile step. you can just `elixir run file.ex` and see your code excute.

in comparision erlang you will need to `erl` to open a REPL then `c(your_module).` then `your_module:your_function().`

when comparing elixir and erlang it's like comparing javascript to C++ but with the same performance.

## simple mental model
immutablity by default. immutability in elixir is not slow as internally it does fast copying. but what it provides to the developer is easy debugging as there are no side effects. this reduces the cognitive load to the developer.

## great up-time
hot code swaps

## concurrency (still learning and not yet knowledgable)

## learning references

- [exercism](https://exercism.org/tracks/elixir)
- [elixir school](https://elixirschool.com/en)
- [elixir docs](https://elixir-lang.org/learning.html)
- [elixir koans](https://github.com/elixirkoans/elixir-koans)
