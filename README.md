# Pipes.js
## Compose functions with Unix like pipes (like Elm / Elixir / F#)

Using pipe operators makes you think about programming as steps of transformations. This compiler will replace the pipe operators with Lo-Dash's chain.


# Usage

#### Define a function
These functions have no knowledge of the chaining system and can be used with or without chaining. The first parameter will always be the data that is passed through the pipeline.

```javascript
function stripChars(str, pattern) {
  return str.replace(pattern, '');
}
```

#### Use functions like Unix pipes
```elixir
# use functions like unix pipe

"hello world " |> String.trim |> String.uppercase
#>>> "HELLO WORLD"

["foo", "bar ", " baz"]
|> Enum.map (x) -> String.upcase(x)
|> inspect
|> take 2

# log ["FOO", "BAR", "BAZ"]
# >>> ["FOO", "BAR"]
```

