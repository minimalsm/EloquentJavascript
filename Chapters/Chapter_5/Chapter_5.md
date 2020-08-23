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

## 5.4 Dominant writing direction
```javascript
function characterScript(code) {
  for (let script of SCRIPTS) {
    if (script.ranges.some(([from, to]) => {
      return code >= from && code < to;
    })) {
      return script;
    }
  }
  return null;
}

function countBy(items, groupName) {
  let counts = [];
  for (let item of items) {
    let name = groupName(item);
    let known = counts.findIndex(c => c.name == name);
    if (known == -1) {
      counts.push({name, count: 1});
    } else {
      counts[known].count++;
    }
  }
  return counts;
}

const dominantDirection = (text) => {
  let scripts = countBy(text, char => {
    let script = characterScript(char.codePointAt(0))
    return script ? script.direction : 'none'
  }).filter(direction => direction != 'none')
	.sort((a, b) => b.count - a.count)
  
  return scripts[0].name
}
```