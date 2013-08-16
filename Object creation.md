# Object Creation

### Factory Pattern:
``` javascript
function a(){
    var obj = {
        b : "Hi! ",
        c : "Bye!"
    };
    return obj;
}

var z = a();                             //i.e z = obj
console.log(z.b, z.c);                   // Hi! Bye!

z.constructor === Object;                // true
z instanceof Object;                     // obvious: every object is instance of Object

z.constructor === obj;
//ReferenceError: 'obj' is undefined because its defined inside 'a'  
                                  
z instanceof obj;                         
// ReferenceError: 'obj' is undefined because its defined inside 'a'
//The problem now is we can't tell which specific object z belongs to.
```  
###Disadvantage:  
It becomes difficult to query for the origin specific object. This can be overcomed by Constructor Pattern  
###Constructor Pattern:
``` javascript  
function A(){
	this.b = "Hi! ";
    this.c = "Bye!";
    this.show = function(){
    	console.log(z.b,z.c);
	};
};

var z = new A();
z.show();
z instanceof A;           //true
z instanceof Object;      //true
A instanceof Object;      //true

var x = new A();
x.show();
```  
###Disadvantage:
Here z and x both have their own copy of show() method i.e. it is not shared hence takes up memory. This can be overcomed by Prototype Pattern.

