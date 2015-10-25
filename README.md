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
```javascript
// trim and capitalize are lo-dash functions

'hello-world ' |> trim |> stripChars('-') |> capitalize
// ->  "Hello world"


var res = '555 121-7878'
|> stripChars('-')
|> stripChars(' ')
|> stripChars('.')

// ->  "5551217878"


result = ['555-111-3333', '555-222-4444', '555-333-5555']
|> map (num) => stripChars(num, '-')
|> inspect
|> take 2

// log ['5551113333', '5552224444', '5553335555']
// ->  ['5551113333', '5552224444']
```

#### Compile to de-sugar into Lo-Dash methods
Run the files through the compiler or webpack-loader.

```bash
npm install pipes-js  # not published yet
pipesjs watch foo.js bar.js
```
or via webpack loader:

```bash
npm install pipes-loader      # not published yet
```

```
var res = _chain('555 121-7878')
.pipes.call(stripChars('-'))
.pipes.call(stripChars(' '))
.pipes.call(stripChars('.')).value()
```
