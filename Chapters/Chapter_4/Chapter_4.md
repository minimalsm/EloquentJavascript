# Chapter 4

## 4.1 The sum of a range
```javascript
const range = (start, end, step = 1) => {
  const nums = []

  if (step > 0) {
    for (let i = start; i <= end; i += step) nums.push(i)
  } else {
    for (let i = start; i >= end; i += step) nums.push(i)
  }

  return nums
}

const sum = (numbers) => {
  let total = 0
  
  for (let el of numbers) {
    total += el
  }

  return total
}
```

## 4.2 Reversing an Array
```javascript
const reverseArray = (arr) => {
  const output = []
  for (let el in arr) {
    output.unshift(arr[el])
  }
  return output
}

const reverseArrayInPlace = (arr) => {
  for (let i = 0; i < Math.floor(arr.length / 2); i++) {
    [arr[i], arr[arr.length - 1 - i]] = [arr[arr.length - 1 - i], arr[i]]
  }
  return arr
}
```
