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
  if(first_index === undefined){
    console.log("Your first index is invalid");
  } else if (second_index === undefined) {
    console.log("Your second index is invalid");
  } else {
    let tmp = array[first_index];
    let tmp2 = array[second_index]
    array[first_index] = array[second_index];
    array[second_index] = array[first_index];
  }
}
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

function reverse(array) {
  let j = array.length;
  for(let i = 0; i < array.length; i++){
    swap(array, i, j)
    j -= 1;
  }
}
```


new answers:

```js
let swapArray1 = [1, 2, 3, 4, 5]
let swapArray2 = [6, 7, 8, 9, 10]

let reverseArray = [1, 2, 3]

let bubbleArray = [4, 8, 2, 9, 3, 5, 7, 6, 8, 1]

swap(swapArray1, swapArray2)

reverse(reverseArray)

bubbleSort(bubbleArray)

function swap(arr1, arr2) {
  console.log("First Array was: " + arr1)
  console.log("Second Array was: " + arr2)
  let arr3 = [];
  for(let i = 0; i < arr1.length; i++){
    arr3[i] = arr1[i];
  }
  for(let i = 0; i < arr2.length; i++){
    arr1[i] = arr2[i]
  }
  for(let i = 0; i < arr2.length; i++){
    arr2[i] = arr3[i]
  }
  console.log("First Array is now: " + arr1)
  console.log("Second Array is now: " + arr2)
}

function reverse(arr1){
  console.log("Array was: " + arr1)
  let arr3 = [];
  let size = arr1.length
  for(let i = 0; i < size; i++){
    arr3[i] = arr1[size-(i+1)]
  }
  arr1 = arr3
  console.log("Array is now: " + arr1)
}

function bubbleSort(arr1){
  console.log("Array was: " + arr1)
  for(let q = arr1.length; q > 0; q--){
    for(let i = 0; i < arr1.length; i++){
      if(arr1[i] > arr1[i + 1]){
        let breaker = arr1[i + 1]
        arr1[i + 1] = arr1[i]
        arr1[i] = breaker
      }
    }
  }
  console.log("Array is now: " + arr1)
}
```
