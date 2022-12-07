**python** kind of methods like len type are not built-in
they are methods/properties of datatypes
e.g. val=7
val.length


**However** there are few built-ins :
typeof val
String(val)

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
${age>30?'Over 30':'Under 30'}



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





























































































































































































































































































































