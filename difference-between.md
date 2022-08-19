
The Difference Between call() and apply() and bind()
---------------------------------------------------
The difference is:
==================
==>The call() method takes arguments separately.

==>The apply() method takes arguments as an array.

==>The bind() methods returns the function.

call() example:-
-------------------

const person = {
  fullName: function(city, country) {
    return this.firstName + " " + this.lastName + "," + city + "," + country;
  }
}

const person1 = {
  firstName:"John",
  lastName: "Doe"
}

person.fullName.call(person1, "Oslo", "Norway");




apply() examples:-
----------------------
const person = {
  fullName: function(city, country) {
    return this.firstName + " " + this.lastName + "," + city + "," + country;
  }
}

const person1 = {
  firstName:"John",
  lastName: "Doe"
}

person.fullName.apply(person1, ["Oslo", "Norway"]);


bind() examples:-
----------------------------
const person1={
firstName:"John",
lastName: "Doe"
}
const person2={
firstName:"karthi",
lastName: "eshwari"
}
const fullname=function(){
  return `welcome ${this.firstname} ${this.firstname}`
}
console.log(fullname.bind(person1)());
........................ (or) .......................                   
const module = {
  x: 42,
  getX: function() {
    return this.x;
  }
};

const unboundGetX = module.getX;
console.log(unboundGetX()); 
// The function gets invoked at the global scope
// expected output: undefined

const boundGetX = unboundGetX.bind(module);
console.log(boundGetX());
// expected output: 42