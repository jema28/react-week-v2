## classes in javascript

if you needed to create many rectangle objects, and they all needed to have height, width and colour you could create them like this:

```js

const rectOne = {height: 800, width: 400, colour: 'red'}
const rectTwo = {height: 999, width: 833, colour: 'orange'}
const rectThree = {height: 300, width: 233, colour: 'blue'}

```

# OR

we could use classes like this:
```js
class Rectangle { // this is a class declaration
  constructor(h, w, c) {
    this.height = h;
    this.width = w;
    this.color = c
  }
}

const rectOne = new Rectangle( 800,  400, 'red')
const rectTwo = new Rectangle( 999,  833, 'orange')
const rectThree = new Rectangle( 300,  233, 'blue')

```



this becomes more useful the more complicated the object is, so for example if there was a method on each object that calculated area: 

```js

const rectOne = {
    height: 800, 
    width: 400, 
    colour: 'red', 
    area: function(){
        return this.height * this.width
  }
}
  
const rectTwo = {
    height: 999, 
    width: 833, 
    colour: 'orange', 
    area: function(){
        return this.height * this.width
  }}
  
const rectThree = {
    height: 300, 
    width: 233, 
    colour: 'blue',     
    area: function(){
        return this.height * this.width
  }}
```

```js
class Rectangle { // this is a class declaration
  constructor(h, w, c) {
    this.height = h;
    this.width = w;
    this.color = c
  }
  
  area() {
    return this.height * this.width;
  }
}

const rectOne = new Rectangle( 800,  400, 'red')
const rectTwo = new Rectangle( 999,  833, 'orange')
const rectThree = new Rectangle( 300,  233, 'blue')

```


## extending classes 

you can extend classes like this:

```js
class Animal { 
  constructor(name) {
    this.name = name;
  }
  animalSpeaks() {
    console.log(`I am an Animal, my name is ${this.name}`);
  }
}

class Dog extends Animal {
  constructor(name, legs) {
    super(name); // this is giving the parameter needed for the animal class 
    this.legs = legs
  }

  dogSpeaks() {
    console.log(` I am dog called ${this.name}. i have ${this.legs} legs`);
  }
}

let d = new Dog('Mitzie',4);
d.animalSpeaks(); // I am an Animal, my name is Mitzie
d.dogSpeaks() // I am a dog called Mitzie. i have 4 legs

```
