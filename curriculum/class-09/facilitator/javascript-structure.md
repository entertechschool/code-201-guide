# JavaScript Structure

1. Declara las Variables Globales 
1. Declara las Funciones constructoras - ¡sus nombres deberá comenzar con mayúsculas!
1. Declara los métodos de prototype
1. Declara las funciones regulares
1. Añade event listeners
1. Llama a las funciones

```javascript
//declare global variables at the top of your file
const globalVariable1 = 'hello';
const globalVariable2 = [0, 1, 2];
const myForm = document.getElementById('my-form');

//create an instance of PersonConstructor and save it to the sam variable
//note that we can do this before the constructor function declaration
const sam = new PersonConstructor('Sam', 'Hamm');
//now sam = { firstName: 'Sam', lastName: 'Hamm' }

//then put any object constructors
function PersonConstructor(first, last) {
 this.firstName = first;
 this.lastName = last;
}

//then put any prototype functions that go with the object constructor
//call this function on an instance of PersonConstructor
PersonConstructor.prototype.sayHello = function() {
 console.log('Hello, my name is ' + this.firstName);
}

//then put regular function declarations
function firstFunction(parameter) {
 console.log(parameter);
}

function secondFunction(myArray) {
 for (i = 0; i < myArray.length; i++) {
  console.log(myArray[i]);
 }
}

function formHandler(event) {
 console.log(event.target);
}

//then add any event listeners
myForm.addEventListener('submit', formHandler);

//finally, call your functions
firstFunction(globalVariable1);
//logs 'hello'
secondFunction(globalVariable2);
//logs  0
//  1
//  2
sam.sayHello();
//logs 'Hello, my name is Sam'
