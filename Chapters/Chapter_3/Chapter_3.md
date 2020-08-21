# Chapter 2

## 3.1 Minimum
```javascript
const min = (a, b) => a >= b ? a : b
```

## 3.2 Recursion
```javascript
const isEven = (n) => {
  if (n === 0) {
    return true
  } else if (n < 2) {
    return false
  } else {
    return isEven(n - 2)
  }
}
```

## 3.3 Bean Counting

```javascript
const countBs = (word) => (
  countChar(word, 'B')
)


const countChar = (word, char) => {
  let count = 0;

  for (let i = 0; i < word .length; i++) {
    if (word [i] == char) count++;
  }

  return count
}
```