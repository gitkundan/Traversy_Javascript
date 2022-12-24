<!-- code : https://github.com/PacktPublishing/Modern-JavaScript-From-The-Beginning/blob/master/V11411_Code%20File/S03/3-4-project-files.zip -->

<!-- https://github.com/PacktPublishing/Modern-JavaScript-From-The-Beginning/blob/master/V11411_Code%20File/S03/3-4-project-files.zip -->

Use the following html template
```html

    <!-- FONT
  –––––––––––––––––––––––––––––––––––––––––––––––––– -->
    <link
      href="//fonts.googleapis.com/css?family=Raleway:400,300,600"
      rel="stylesheet"
      type="text/css"
    />

    <!-- CSS
  –––––––––––––––––––––––––––––––––––––––––––––––––– -->
    <link rel="stylesheet" href="./css/normalize.css" />
    <link rel="stylesheet" href="./css/skeleton.css" />

    <!-- Favicon
  –––––––––––––––––––––––––––––––––––––––––––––––––– -->
    <link rel="icon" type="image/png" href="images/favicon.png" />
```

**python** kind of methods like len type are not built-in
they are methods/properties of datatypes
e.g. val='london'
val.length

**However** there are few built-ins :
typeof val
String(val)

**Getting help**
like python dir() JS has console.dir
e.g.
console.dir(window)
console.dir(window.console)
console.dir(window.sayHello) 

**To complicate further - Casting** 
=====================================================
casting can be done both via individual 
object method or via built-in method
val=(5).toString()
value=(true).toString()
val=String(5)
=====================================================
Date constructor : date=new Date() --> creates date object

=====================================================
**Template Literal**
pythonic differences : use backticks and ${variable_name} syntax
like python lets you do functions and conditionals inser {}
${hello()}

const name='John'
const age = 30
const job = 'Web developer'
const city = 'Miami'
let html

data = `
<ul>
    <li>Name: ${name}</li>
    <li>Age: ${age}</li>
    <li>Job: ${job}</li>
    <li>City: ${city}</li>
</ul>

`
document.body.innerHTML=data
=====================================================
**Ternary Operator / Conditional Expression**
data=${age>30?"Over 30":"Under 30"}
console.log(data)

=====================================================
**Array and array methods i.e. list methods**

constructors : both of these will work
const numbers = [5,45]
const numbers2 = new Array(3,4)

numbers.length
Array.isArray(numbers)

val=numbers.indexOf(5) => gives index position
numbers.push(3)
numbers.unshift(4)
numbers.pop(5)
numbers.splice(2,5)
numbers.reverse()
numbers.concat(numbers2)

**numbers.sort()**

The JavaScript Array .sort() function by default converts the array elements to strings before making comparisons.

You can override that:

x.sort(function(e1, e2) { return e1 - e2; });
(The function passed should return a number that's negative, zero, or positive, according to whether the first element is less than, equal to, or greater than the second.)

I've never seen a rationale for this odd aspect of the language.

It's because .sort() has to work with any type of data by default, including mixed types. The generic function would have to check the whole array to see if it's all numbers in order to be smarter

=====================================================
**Object literals i.e. dictionary methods**
object is instance of class but you can write the object directly like dict; these are called object literal i.e. object not created from class

difference from json : json keys are strings (double quotes) and no functions in json but possible in object literal

const person={
    firstName: 'Steve',
    lastName: 'Nely',
    hobbies: ['sss','ssss','dfsadfsa'],
    address: {
        city: 'bethlem',
        town: FD
    },
    get BirthYear: function (){
        return 2017 - this.age
    }
}

let val
val = person
val = person.firstName
val=person.address.state
val=person.getBirthYear()

=====================================================
**Dates and Times**
const birthday=new Date('Dec 12 2022')
const today=new Date() //will give today

val=today.getMonth()

birthday.setMonth(2)
birthday.setDate(12)

=====================================================
**If else**
if (id===100){
    console.log('Correct')
} else {
    console.log('incorrect')
}

**Ternary Operator**
condition?true_value:false_value
age<12?console.log('he is teenage'):console.log('He is adult')
alternatively, console.log(id === 100 ? 'CORRECT':'INCORRECT')

and is && e.g. if (age>12 && age <19)
or is || e.g. if (age >12 || age >90)

=====================================================
**Switches**
Case statement

switch(color){
    case 'red':
     console.log('color is red')
     break
    case 'blue':
     console.log('color is blue')
    default:
     console.log('Color is neither blue or red')
     break
}

Another example : inside the condition you can put functions/objects

let day

switch(new Date().getDay()){
    case 0:
     day = 'Sunday'
     break
}

=====================================================
**Functions**
**Function Declaration**
function greet(firstName='John', lastName='Doe'){
    return `Hello ${firstName} ${lastName}`
}

console.log(greet())
console.log(greet('James','Bowden'))
console.log(greet(firstName='John',lastName='Bowden'))

**Function Expression**
assign the function definition to a variable
const square = function(x=3){
    return x*x
}

console.log (square())

*FE better than FD for closure and hoisting*

**IIFE**
define lambda function and call it in one go,
so variable declaration/private methods inside scope
like namedtuple rather than full blown class
will revisit in module pattern (calorie counter)

(function(){
    console.log('IIFE Ran')
})()

Alternatively,
(()=>console.log('IIFE Ran'))()

another example with parameters:
((firstName,lastName)=>`Hello ${firstName} ${lastName}`)(firstName='medusa',lastName='oblongata')

=====================================================
**Loops**
array=[10,20]
for (let i = 0; i < array.length; i++) {
    const element = array[i];
    console.log(element);

    if (i == 3) {
        console.log('3 is my favourite number')
        continue //how to carry on 
    }

    if (i == 5) {
        console.log('Stop the loop')
        break //how to exit the loop
    }

*array iterator(for each)*
const cars=['Ford','Chevy','Honda']
cars.forEach(function (car) {
    console.log(car)})

Alternatively,
const cars=['Ford','Chevy','Honda']
cars.forEach(car=>console.log(car))


*object literal iterator (for in)*





=====================================================
**OOP**
```javascript
function Person(name){
    this.name=name
    this.location='London'
    console.log(this); //produces the object for the currently instantiated object
}

const brad = new Person('brad')
```

the above function is object constructor for Person() class ==> ES6 class is syntactic sugar for the above function

```javascript
console.log(this); //this is in global scope
```
will result in window object


ES6 class is syntactic sugar for constructor function : Class keyword started from ES6.
```javascript
class Person{
    constructor(firstName,lastName) {
        this.firstName=firstName
        this.lastName=lastName
    }

    greeting() {
        return `Hello there ${this.firstName} ${this.lastName}`
    }

    //static methods dont need anything from class
    static addNumbers(x,y){
        return x+y
    }
}

const mary = new Person('Mary','Shelley');
console.log(mary.greeting());

//to use static method directly use from class
console.log(Person.addNumbers(1,2));
```

## Inheritance
use extends....
```javascript
//base class
class Person {
    constructor(firstName, lastName) {
        this.firstName = firstName
        this.lastName = lastName
    }

    greeting() {
        return `Hello there ${this.firstName} ${this.lastName}`
    }
}


//child class
class Employee extends Person {
    constructor(firstName, lastName, id) {
        super(firstName, lastName) //call the parent class constructor
        this.id = id
    }

    //method overriden
    greeting() {
        return `Hello there, ${this.firstName} ${this.lastName}. Your id is ${this.id}`
    }
}
const paru = new Employee('Paru', 'Chawla', 34)
console.log(paru.greeting());
```

**Book List Example App**
div for each UI element
label and input tags under the same div
use skeleton css



**Asynchronous**
XHR and Fetch are browser API

XHR: older browser API
Fetch : modern browser API
Axios : Third party library

```javascript
//XHR way
const urlCategories = "https://api.chucknorris.io/jokes/random?category=";

document.querySelector(".get-jokes").addEventListener("click", getJokes);

function getJokes(e) {
  //Create a XHR object, similar to creating a session object
  e.preventDefault();

  const genre = document.getElementById("genre").value;

  xhr = new XMLHttpRequest();
  url = `${urlCategories}${genre}`;
  //make a GET request : third parameter is IfAsync?
  xhr.open("GET", url, true);
  xhr.onload = function () {

    // Check http status
    if (this.status == 200) {
      const joke = JSON.parse(this.responseText);
      console.log(joke.value);
      const output = `
      <ul>
        <li>${joke.value}</li>
      </ul>
      `;
      document.querySelector(".output").innerHTML = output;
    }
  };
  xhr.send();
}

```
=====================================================
**Fetch API**

const url='https://api.github.com/users/deekshasharma'
// test = fetch(url) // comes back not with data but with promise

// what is promise
// promise has a state(pending,fullfilled) and a response object and can be chained to .then
//fetch uses async pattern to get a response object
//bonsailabs has good tutorials
//then also returns a promise not actual data
//so you have to use another .then in chain to retrieve data
fetch(url)
  .then(response => response.json())
  .then(jsonData=>console.log(jsonData))
// console.log(test);

*similar to pandas method chaining / powershell pipeline; where the left function's result gets passed to right function as argument. async-await is syntactic sugar on promise; makes code easy to read as-if synchronous code*

=====================================================
**async-await**

```javascript

async function getUsers() {
  url='https://jsonplaceholder.typicode.com/users/1'

  //get a promise
  const response = await fetch(url)

  //only proceed once the promise is resolved
  // data is promise
  const data = await response.json()

  // only proceed once second promise is resolved
  return data

}

// chain the return value of function with .then to process the results
getUsers().then(users=>console.log(users))

//pattern is 1 async keyword before function and then 2 await inside function and .then in the calling code to handle the promise

//async-await function returns promise NOT data
```

=====================================================
**Arrow function**
```javascript

//one line return with no parameter
sayHello=()=> 'Hello'

//one line return with one parameter
sayHello=name=>`Hello ${name}`
console.log(sayHello('John'));
```

=====================================================
**TBD**
```javascript
TBD

```



































































































































































































































































































=====================================================
*DOM Manipulation*
**Document Traversal**

console.dir(document.body) will give the body hierarchy that contains both childNodes (NodeList) and children (HTML Collection). Nodelist will include comment, text i.e. non HTML as they are also valid nodes. However since we need to get only html elements we will only deal with children


**Document Selector**
document.querySelector ==> returns the target node
item=document.querySelector('.black') ==> selects FIRST element from class black
item=document.querySelector('#213') ==> selects FIRST element with id as 213
item=document.querySelector('h5') ==> selects FIRST element with tag as h5
. for selecting by class
# for selecting by id


document.querySelectorAll ==> returns nodelist (not HTMLCollection)

Others:
document.getlementbyId() ==> returns the html element
document.getelementbyClass()
document.getelementbyTag()


**Changing style**

If the text between html tags need changing use innerText:
    document.querySelector('h1').innerText='Good Day'

If the enclosing tags i.e. whole html needs changing use innerHTML
    document.querySelector('h1').innerHTML='<h3> Good Day </h3>'


```html
<!DOCTYPE html>
<html>
  <body>
    <script>
      function toggleDisplay(){
        let p = document.getElementById("magic");
        if(p.style.display === "none") {
          p.style.display = "block";
        } else {
          p.style.display = "none";
        }
      }
    </script>
    <p id="magic">I might disappear and appear.</p>
    <button onclick="toggleDisplay()">Magic!</button>
  </body>
</html>
```