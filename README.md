# Call-Apply-Bind-Method
//Call:
//It can be used to invoke (call) a method with an owner object as an argument (parameter)
//while calling a function, 1st parameter describes object name to call and 2nd, 3rd .. parameters are acts as an argument to the function.
//Arguments re seperated by ,

let name1={ firstName : 'priya', 
            lastName : 'R', 
            fullName : function(city,state){ 
                         console.log(this.firstName + " "+ this.lastName + " from " + city + " " + state )
}};

let name2 ={firstName: 'vijaya', 
            lastName : 'B'}

name1.fullName.call(name1,'chennai','tamilnadu');//o/p: priya R from chennai tamilnadu
name1.fullName.call(name2,'madurai','tamilnadu');//O/p: vijaya B from madurai tamilnadu

//Apply:
//Apply method is same as a call method, and the arguments are passed trow array method.
name1.fullName.apply(name1,['salem','tamilnadu']); // o/p:priya R from salem tamilnadu

//Bind:
//Bind will create a new function to call a function with this value
//bind() method will provide an argument to the function bind() when it is called on.
let printName =name1.fullName.bind(name2,'vellore','tamilnadu');
console.log(printName);// o/p:ƒ (city,state){ 
 //   console.log(this.firstName + " "+ this.lastName + " from " + city + " " + state )
//}
printName(); //o/p: vijaya B from vellore tamilnadu
