/****

To start with, let's give you a simplistic, high-level view of what Object-oriented programming (OOP) is. We say simplistic, because OOP can quickly get very complicated, and giving it a full treatment now would probably confuse more than help. The basic idea of OOP is that we use objects to model real world things that we want to represent inside our programs, and/or provide a simple way to access functionality that would otherwise be hard or impossible to make use of.

Objects can contain related data and code, which represent information about the thing you are trying to model, and functionality or behavior that you want it to have. Object data (and often, functions too) can be stored neatly (the official word is encapsulated) inside an object package (which can be given a specific name to refer to, which is sometimes called a namespace), making it easy to structure and access; objects are also commonly used as data stores that can be easily sent across the network.

******/

/*****

There are certain features or mechanisms which makes a Language Object Oriented like:

Object
Classes
Encapsulation
Inheritance

*****/

/*****

Object– An Object is a unique entity which contains property and methods. For example “car” is a real life Object, which have some characteristics like color, type, model, horsepower and performs certain action like drive. The characteristics of an Object are called as Property, in Object Oriented Programming and the actions are called methods. An Object is an instance of a class. Objects are everywhere in JavaScript almost every element is an Object whether it is a function,arrays and string.
Note: A Method in javascript is a property of an object whose value is a function.
Object can be created in two ways in JavaScript:
Using an Object Literal
filter_none
brightness_4
//Defining object 
let person = { 
    first_name:'Mukul', 
    last_name: 'Latiyan', 
  
    //method 
    getFunction : function(){ 
        return (`The name of the person is  
          ${person.first_name} ${person.last_name}`) 
    }, 
    //object within object 
    phone_number : { 
        mobile:'12345', 
        landline:'6789'
    } 
} 
console.log(person.getFunction());  
console.log(person.phone_number.landline); 

Using an Object Constructor:
filter_none
brightness_4
//using a constructor 
function person(first_name,last_name){ 
   this.first_name = first_name; 
   this.last_name = last_name; 
} 
//creating new instances of person object 
let person1 = new person('Mukul','Latiyan'); 
let person2 = new person('Rahul','Avasthi'); 
  
console.log(person1.first_name); 
console.log(`${person2.first_name} ${person2.last_name}`); 

Using Object.create() method: The Object.create() method creates a new object, using an existing object as the prototype of the newly created object.
filter_none
brightness_4
// Object.create() example a 
// simple object with some properties 
const coder = { 
    isStudying : false, 
    printIntroduction : function(){ 
        console.log(`My name is ${this.name}. Am I  
          studying?: ${this.isStudying}.`) 
    } 
} 
// Object.create() method 
const me = Object.create(coder); 
  
// "name" is a property set on "me", but not on "coder" 
me.name = 'Mukul';  
  
// Inherited properties can be overwritten 
me.isStudying = 'True';  
  
me.printIntroduction(); 

*****/

/****

Classes– Classes are blueprint of an Object. A class can have many Object, because class is a template while Object are instances of the class or the concrete implementation.
Before we move further into implementation, we should know unlike other Object Oriented Language there is no classes in JavaScript we have only Object. To be more precise, JavaScript is a prototype based object oriented language, which means it doesn’t have classes rather it define behaviors using constructor function and then reuse it using the prototype.
Note: Even the classes provided by ECMA2015 are objects.


Lets use ES6 classes then we will look into traditional way of defining Object and simulate them as classes.

filter_none
brightness_4
// Defining class using es6 
class Vehicle { 
  constructor(name, maker, engine) { 
    this.name = name; 
    this.maker =  maker; 
    this.engine = engine; 
  } 
  getDetails(){ 
      return (`The name of the bike is ${this.name}.`) 
  } 
} 
// Making object with the help of the constructor 
let bike1 = new Vehicle('Hayabusa', 'Suzuki', '1340cc'); 
let bike2 = new Vehicle('Ninja', 'Kawasaki', '998cc'); 
  
console.log(bike1.name);    // Hayabusa 
console.log(bike2.maker);   // Kawasaki 
console.log(bike1.getDetails());


// Defining class in a Traditional Way. 
function Vehicle(name,maker,engine){ 
    this.name = name, 
    this.maker = maker, 
    this.engine = engine 
}; 
  
Vehicle.prototype.getDetails = function(){ 
    console.log('The name of the bike is '+ this.name); 
} 
  
let bike1 = new Vehicle('Hayabusa','Suzuki','1340cc'); 
let bike2 = new Vehicle('Ninja','Kawasaki','998cc'); 
  
console.log(bike1.name); 
console.log(bike2.maker); 
console.log(bike1.getDetails()); 

*****/

/*****

Encapsulation – The process of wrapping property and function within a single unit is known as encapsulation.
Let’s understand encapsulation with an example.
filter_none
brightness_4
//encapsulation example 
class person{ 
    constructor(name,id){ 
        this.name = name; 
        this.id = id; 
    } 
    add_Address(add){ 
        this.add = add; 
    } 
    getDetails(){ 
        console.log(`Name is ${this.name},Address is: ${this.add}`); 
    } 
} 
  
let person1 = new person('Mukul',21); 
person1.add_Address('Delhi'); 
person1.getDetails(); 

****/

/****
Inheritance – It is a concept in which some property and methods of an Object is being used by another Object. Unlike most of the OOP languages where classes inherit classes, JavaScript Object inherits Object i.e. certain features (property and methods)of one object can be reused by other Objects.
Lets’s understand inheritance with example:
filter_none
brightness_4
//Inhertiance example 
class person{ 
    constructor(name){ 
        this.name = name; 
    } 
    //method to return the string 
    toString(){ 
        return (`Name of person: ${this.name}`); 
    } 
} 
class student extends person{ 
    constructor(name,id){ 
        //super keyword to for calling above class constructor 
        super(name); 
        this.id = id; 
    } 
    toString(){ 
        return (`${super.toString()},Student ID: ${this.id}`); 
    } 
} 
let student1 = new student('Mukul',22); 
console.log(student1.toString());

*****/
