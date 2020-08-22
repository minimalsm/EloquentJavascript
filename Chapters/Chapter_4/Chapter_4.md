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
