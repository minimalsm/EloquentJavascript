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