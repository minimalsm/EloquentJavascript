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