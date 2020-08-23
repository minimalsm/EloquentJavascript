# Chapter 5

## 5.1 Flattening
```javascript
const flatten = (arr) => (arr.reduce((a, b) => a.concat(b)))
```

## 5.2 Your own loop
```javascript
const loop = (start, test, update, body) => {
  let v = start
  
  while (test(v)) {
    body(v)
    v = update(v)
  }
}
```

## 5.3 Everything
```javascript
const everyForOfLoop = (arr, condition) => {
  let output = true
  for (let element of arr) {
    if (!condition(element)) return output = false
  }
  return output
}

const everyForLoop = (arr, condition) => {
  for (let i = 0; i < arr.length; i++) {
    if (!condition(arr[i])) return false
  }
  return true
}

const everySome = (arr, condition) => !arr.some((el) => !condition(el))
```