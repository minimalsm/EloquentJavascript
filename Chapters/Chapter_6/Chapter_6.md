# Chapter 6

## 6.1 A vector type
```javascript
class Vec {
  constructor(x, y) {
    this.x = x;
    this.y = y;
  }
  plus(vector) {
    let x = this.x + vector.x;
    let y = this.y + vector.y;
    return new Vec(x, y)
  }
  minus(vector){
    let x = this.x - vector.x;
    let y = this.y - vector.y;
    return new Vec(x, y)
  }
  get length(){
    return Math.sqrt(Math.pow(this.x, 2) + Math.pow(this.y, 2))
  }
}
```

## 6.2 Groups
```javascript
class Group {
  constructor() {
    this.collection = []
  }
  delete(item) {
    this.collection = this.collection.filter((el) => el != item)
  }
  add(item) {
    this.has(item) ? null : this.collection.push(item)
  }
  has(item) {
    return this.collection.includes(item)
  }
  static from(collection) {
    let group = new Group
    for (let element of collection) {
      group.add(element)
    }
    return group
  }
}
```

## 6.3 Iterable groups

```javascript
Group.prototype[Symbol.iterator] = function() {
  return new GroupIterator(this);
};

//Instead of the above, this could be added to the
//Group class to set it's iterator 
  // [Symbol.iterator]() {
  //   return new GroupIterator(this);
  // }

class GroupIterator {
  constructor(group) {
    this.i = 0
    this.group = group;
  }

  next() {
    if (this.i === this.group.collection.length) return { done: true }

    let value = this.group.collection[this.i]
    this.i++

    return { value, done: false }
  }
}
```