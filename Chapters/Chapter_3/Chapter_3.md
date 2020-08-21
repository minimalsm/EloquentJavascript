# Chapter 2

## 3.1 Minimum
```javascript
const min = (a, b) => a >= b ? a : b
```

## 3.2 Recursion
```javascript
const isEven = (n) => {
  console.log(n)
  if (n === 0) {
    return true
  } else if (n < 2) {
    return false
  } else {
    return isEven(n / 2)
  }
}
```