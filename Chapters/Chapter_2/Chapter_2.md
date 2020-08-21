# Chapter 2

## 2.1 Looping a triangle

```javascript
const triangleLoop = () => {
  for (let line = '#'; line.length <= 7; line += '#') {
    console.log(line)
  }
}
```

## 2.2 FizzBuzz
Immediate solution
```javascript
const fizzBuzz = () => {
  for (let i = 1; i <= 100; i++) {
    if (i % 5 === 0 && i % 3 === 0) {
      console.log('FizzBuzz')
    } else if (i % 3 === 0) {
      console.log('Fizz')
    } else if (i % 5 === 0) {
      console.log('Buzz')
    } else {
      console.log(i)
    }
  }
}
```

A slightly more elegant solution
```javascript
const fizzBuzzTwo = () => {
  for (let i = 1; i <= 100; i++) {
    let result = ''
    i % 3 === 0 ? result += 'Fizz' : ''
    i % 5 === 0 ? result += 'Buzz' : ''
    console.log(result || i)
  }
}
```

## 2.3 Chessboard
```javascript
const chessBoard = (size = 8) => {
  let str = ''

  for (let col = 0; col < size; col++) {
    for (let row = 0; row < size; row++) {
      (row + col & 1) ? str += '#' : str += ' '
    }
    if (col < (size - 1)) str += '\n' //don't print a new line after the last line
  }

  console.log(str)
}
```
