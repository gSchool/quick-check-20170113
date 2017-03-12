# Quick Check

- For this pop quiz, feel free to use your editor/repl.it to write and VERIFY your answer.
- Paste your answer into the appropriate place below when you are done.
- *LOOK* at the examples provided to determine the expected behaviour of your function.
- Your answer MUST work in the examples provided.

## Standard: Solve problems that require swapping

### Write a function that swaps two elements in an array

- DO NOT access scope outside of the function

```js
var numbers = [2, 1]
swap(numbers, 1, 0)
console.log(numbers) // [1, 2]

var objects = [{first_name: "Busta"}, {last_name: "Carey"}, {first_name: "Mariah"}, {last_name: "Rhymes"}]
swap(objects, 1, 3)
console.log(objects) // [{first_name: "Busta"}, {last_name: "Rhymes"}, {first_name: "Mariah"}, {last_name: "Carey"}]

var empty = []
swap(empty, 1, 3)
console.log(empty) // []

var one = [1]
swap(one, 0, -1)
console.log(one) // [1]
swap(one, -1, 0)
console.log(one) // [1]

function swap(array, first_index, second_index) {
  var temp = array[first_index]
  array[first_index] = array[second_index]
  array[second_index] = temp
  return array
}
swap(objects, 1, 3)
```

### Write a function that reverses an array in place, using the above `swap()` function

- Implement the function using only (but not necessarily all)
  - basic operations (`[]`, `+`, `-`, `++`, `let`, etc.)
  - loops
  - `Array.length`
  - the `swap()` function that you wrote above
  - the `Math` library
- The function must be as efficient as possible

```js
var odds = [3, 9, 7, 5]
console.log(odds) // [3, 9, 7, 5]
reverse(odds)
console.log(odds) // [5, 7, 9, 3]

var evens = [2, 8, 6, 4, 10]
console.log(evens) // [2, 8, 6, 4, 10]
reverse(evens)
console.log(evens) // [10, 4, 6, 8, 2]

// Hey, the world has evolved into the 21st century :/

function reverse(array) {
  let i = 0
  while ( i < ((array.length - 1) / 2)) {
    swap(array, i, (array.length - i - 1))
    i++
  }
}
reverse(evens)
```
