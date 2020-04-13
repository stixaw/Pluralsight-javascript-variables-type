# GetYourLoanApp

![enter image description here](https://www.pluralsight.com/content/dam/pluralsight/newsroom/brand-assets/logos/pluralsight-logo-vrt-color-2.png)  

Hi! 

Welcome to the GitHub repository of the GetyourLoanApp application.
This app is the demo app for the Pluralsight course [JavaScript Variables and Types](https://app.pluralsight.com/library/courses/javascript-variables-types/).

You can download a copy of the code and follow along in the course.

The application consists out of a simple HTML file, with some CSS and, most importantlty, a JavaScript file. 

# Javascript Variables and Types
## Module 2
### Using Variables, Literals and Assignments

#### Using Tagged Template Literals
example:
```javascript
    var summaryText = String.raw`Dear ${la.ApplicantName}, //String.raw is the tag
    Your application for ${"$" + la.LoanAmount}, ${reviewText}
    Your risk profile is ${riskProfile}
    Your unique application code is \t${createApplicationId()}
    `;
```

#### Difference between let and const

* var 
    - has no block scope
    - Can be redeclared anywhere
    - Can be used and reassigned anywhere
* let 
    - has a block scope
    - Can NOT be redeclared within scope
    - Can be reassigned within scope
* const 
    - has a block scope
    - Can NOT be reassigned or redeclared
    - The value it references CAN be changed

#### Destructuring Syntax

example:
```javascript 
var [isEmployed, hasKids, hasLoans, hasCreditCards] = riskFactors;

//destructuring with Object
var {
    Id,
    ApplicantName,
    ApplicantDateOfBirth,
    ApplicantAnnualIncome,
    Factors,
    LoanPurpose,
    LoanAmount
} = la;
```

-------------------------------------------------
## Module 3
### Applying Primitive Types

#### Test Strings for Specific Content
string.includes
string.startswith
.trim()
.toLowerCase()
string.search

#### Test Numbers for Type and Safety

Number.isInteger
Number.isSafeInteger

#### Symbols

```javascript
let id = Symbol()
or
let id = Symbol('myId')

console.log(id) //symbol

console.log(id.toString()) //Symbol(myId)
```

* Symbols are unique
* Symbols you can retreive exsiting Symbols
* When would you use it?
  - you can use them to create a property on an object
  - keeps it hidden
  - access it using Symbol.for

example:
```javascript
let loan = {
    name: "Barry",
    [Symbol("income")]: 15000
};

console.log(loan[Symbol.for("income")]);
console.log(Oject.getOwnPropertyNames(loan)) // will  not return symbol