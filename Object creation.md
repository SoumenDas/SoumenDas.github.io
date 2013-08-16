# Object Creation

### Factory function:
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
It becomes difficult to query for the origin specific object. This can be overcomed by Constructor function  
###Constructor function:
``` javascript  
function A(){
	this.b = "Hi! ";
    this.c = "Bye!";
};

var z = new A();
console.log(z.b, z.c); 
    
```

