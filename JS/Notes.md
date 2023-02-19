# Call Bind and Apply

* Call is a function that helps you change the context of the invoking function. In layperson's terms, it helps you replace the value of this inside a function with whatever value you want.

* Apply is very similar to the call function. The only difference is that in apply you can pass an array as an argument list.

* Bind is a function that helps you create another function that you can execute later with the new context of this that is provided.

## Example:

    var car = { 
        registrationNumber: "GA12345",
        brand: "Toyota"
    }

    function displayDetails(ownerName) {
        console.log(ownerName + ", this is your car: " + this.registrationNumber + " " + this.brand);
    }

    displayDetails.apply(car, ["Ashish"]);
    displayDetails.call(car, "Tanuj"); 
    // var bindFn= displayDetails.bind(car)
    // bindFn('Harshit')

    displayDetails.bind(car)('Harshit'); 

# What is callback function in JavaScript?
A callback is a function passed as an argument to another function. This technique allows a function to call another function. A callback function can run after another function has finished.

## Example:
// Callback Function Example
function greet(name, myFunction) {
    console.log('Hello world');
    myFunction(name);
}

// callback function
function sayName(name) {
    console.log('Hello' + ' ' + name);
}

// calling the function after 2 seconds
setTimeout(greet, 2000, 'John', sayName);

greet('Tanuj',sayName)

