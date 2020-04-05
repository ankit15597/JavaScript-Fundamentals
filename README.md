# JavaScript-Fundamentals 

                                JAVASCRIPT(JS)  NOTES
Data types in JS:




- Everything in JS except Primitive data types is object.
- In JS, we don’t have a character data type. ‘ ‘ and “ “ both are used to contain string.
- Escape character \ is used to escape a character. Used when we want “ or ‘ itself in a string.
 Ex: var a = “Ankit\”Gupta”; console.log(a); o/p: Ankit”Gupta
- Unlike C and Java, we don’t have int,float,double and long. We have just one data type i.e number
 Which stores every number as 64 bit.
- Falsy values: The values which are treated as false in JS: 
1.Undefined   
2. 2. Null 
3. 3. 0  
4.4. NaN  
5.5. “ “ (Empty string)
- In JS, we can use comparison operator to compare strings also. They get compared a/c to dictionary(lexicographical order)
Ex: “aa” < “ab”; Evaluates to true. 

Functions in JS:

Unlike C and Java, we don’t have to specify the type of function parameters and the return type, since JS is dynamically typed language and the return type and the type of parameters gets assigned during run time. 

Ex: function add(a,b) {
return a+b;
}
   
If we don’t return anything from a function, then that doesn’t mean that the return type of the function becomes void. It still returns the value: “undefined”.

- In JAVA, we have a block scope but in JS we have a function scope. That is, a variable declared anywhere in the function, is accessible throughout the function. Ex:  
x is defined inside if block but can be accessed from else block as well.

- But still, the best approach is to define all the variables to be used in a function, right at the start of the function body.

- Javascript inside html:

JS code can be typed in HTML under <script></script> tag. This tag can be placed under head or in body.

- We can put multiple script tags in a HTML file but the best practice is to keep all the JS code under  
 a single script tag.

- It’s executed in HTML from top to bottom.


Switch case in JS:

If the value inside switch matches any of the labels, then that particular code is executed,
Else default is executed.





Objects in JS:

- Objects are un-ordered collection of properties, and each property has a name and a value.

- Each property has a name and a value.
- The property names are strings and the value associated with it can be of any data type.
- It could be primitive type of value or other object.
- It’s not required to put the property name under double quotes.

Sample snippet: 

var a = {car:"lamborghini",color:"red"};
Undefined
a
{car: "lamborghini", color: "red"}

typeof(a)

"object"
a.wheels = "CEAT tyres";
"CEAT tyres"
a;

{car: "lamborghini", color: "red", wheels: "CEAT tyres"}

V.imp:
We can add new property to an object using [ ], as if the title of the property was some kind of index of an array. 

Ex: a[“engine horsepower”] = 700;

- Such kind of notation is useful, when iterating over the values of object (via forIn loop)







- For in loop is specially made to iterate over the property of the objects.
- Was it not there, we will have to give print command for each property to print it’s value.
- Note: There’s no index and length in Object data type, hence we can’t use normal for loop to iterate over the properties present inside an object.

Ex: var sampleobj = {title:"Ankit", lastname: "Gupta", hobby: "coding", fav:"Netflix"}

For In loop:

for (var p in sampleobj) {                //fetches each property title in var p
console.log ( sampleobj [p] );            //title is passed as index to get the value.

}
O/p: Ankit
 Gupta
Coding
Netflix

- ForEach Loop

- ForEach() is a function which takes another function as it’s parameter, the function inside forEach is called for each element of the array.
- To access the content of array, we need to pass a parameter inside the anonymous function in which the respective value of each array item gets stored in respective iteration.
- Used to iterate over each value of array. 
Syntax: var a = [1,2,3,4,5];
a.forEach(fucntion(el){console.log(el)}); 

Note: ForEach() used to iterate over arrays while For In is used to iterate over objects.

JSON (Javascript Object Notation)

- JSON is like a javascript object used to send data from server to JS.
- Each property inside a JSON object must be put inside a double quotation.
- JSON is basically like an XML string.

Use: https://jsonlint.com/ to validate your JSONs.

Syntax: { “title”: ”Ankit”, “roll”:4 }

Note: In JSON object, single quotes are not allowed for object properties.
However number can be written as it is.

- Now store the JSON in JS as a string in single quotes, else we have to use escape character to escape the double quotes inside the JSON.

var sample_json  =  ‘ { “title”: ”Ankit”, “roll”: 4 } ‘ 

- JSON.parse() method takes the JSON string and returns the Javascript object.

Ex: var yo = JSON.parse(sample_json);

Console.log(yo.title) ;  o/p: Ankit


More Object concepts:

- We can put array, object and function inside an object.

Ex:   var a = {
           color: [“blue”, ”green”, "red", ”yellow”]             //array inside object
          , fname: "ankit"                                 // Normal property value
          , lname: "gupta"                                // Normal property value
          , salary: function()         {                    // Function inside object
                                     return 33000;
                                  }
          , fullname: function() {                          //Function inside object
                      
                       return this.fname + " " + this.lname;
                            }
          , living: {city: "Bangalore", country: "India"}        //Object inside Object
}
// this is used to refer to the owner of the object. Here the owner is variable a.
  Now this.fname refers to the property fname of variable a.

To call function inside objects: a.salary(); , a.fullname(); 
To call array inside object: varName.propertyName[index];
To call object inside object: varName.propertyName.propertyName;
Ex: a.living.city; o/p: Bangalore
Array of Objects:

- We can put objects inside an array and it will be treated as an array of objects.
Ex: 
var student = [


    {name: "Ram", age:25},
    {name: "Ankit", age: 22},
    {name: "Sanchit", age:20}
    
    ]

How to access elements of this array?
Sol:  console.log(student[0].age + " " + student[0].name)
O/p:  25 Ram

Using For loop:
for (var i = 0 ; i<student.length ; i++){
    console.log(student[i].name + " " + student[i].age);
}
O/P: 
 Ram 25
 Ankit 22
 Sanchit 20

Array Methods: MAP() 

- Used to take out another array from an array and is stored as new array. No change on original array is performed.

Ex: var a = [1,2,3,4,5]
   var b = a.map(function(x){return x*10;})  // Note: The function can also be declared outside.
O/p: [10, 20, 30, 40, 50]











Javascript Inbuilt Methods:



Math Functions: 
 In all the math functions we need to call give prefix Math. Ex: Math.ceil()



Javascript date methods:

Note: Before using the date methods, we need to create a date object first, store it in a variable and then call the specific date method on that variable.

Ex: var a = new Date();
   var b = a.toDateString();
   console.log(b);         o/p: "Sat Apr 04 2020"


















JS: DOM (Document Object Model)


- In JS, the HTML is loaded as a DOM tree, which has root (parent)node as document and head and body has child nodes. 

- The title tag inside head is child node of head and the text inside title element is child of text.

- This model is used to GET, SET, ADD and DELETE HTML tags/values.


DOM Targeting Methods





































