## Language

### Introduction ✔️

-   What is a programming language?
-   Javascript or ECMAscript? (brief history of JS)
-   Interpreted languages vs. compiled languages (quick overview)

### Variables: Running js files with node ✔️

-   Variables: introducing `var`, `let`
-   Constants: introducing `const`
-   Declaration and assignment: `undefined` and `var` hoisting
-   A word about naming conventions: camelCase vs. snake_case
-   Syntax debugging II: Undeclared variables

### Data Types: An introduction ✔️

-   Primitive Data Types: Numbers, Strings, Boolean, Null and Undefined
-   Empty variables: `null` vs. `undefined`.
-   Objects: Arrays and Objects
-   Data type: the unary operator `typeof`

### Statements ✔️

-   Definition of statement: The semicolon `;`
-   Hello world: `console.log(<expression>)`
-   Comments: `//`, `/* */`
-   Syntax Debugging I: Unclosed parentheses

### Expressions ✔️

-   String expressions: single quotes, double quotes, concatenation
-   Mathematical expressions: +, -, \*, /, %
-   Boolean expressions: comparison operators (`===, !==, >=, <=, >, <`)
-   Conditional expressions: the ternary operator (combining the examples above)

### Changing variables ✔️

-   Variable reassignment: `=`, `+=`, `-=`, string accumulation
-   Counting iterations: the counter variable, `++`, `--`
-   Reading a program I (first introduction to state: The values of all variables at any given point)
-   Conditional assignment with the ternary operator
-   Syntax debugging III: Reassigning constants

### String ✔️

-   Escaping special chars: `\'`, `\`, `\n`
-   Syntax debugging IV: Strings and quotes
-   String interpolation: template literals, using expressions within strings
-   Syntax debugging V: Unclosed quotation marks
-   Getting the length of a string: `String.prototype.length`
-   Getting a character in a string: bracket notation
-   Syntax debugging VI: Unclosed brackets

### Basic String Methods ✔️

-   Converting case with:

`String.prototype.toUpperCase()`, `String.prototype.toLowerCase()`

-   Extracting parts of a string: `String.prototype.substring()`
-   Checking if a string is inside another string: `String.prototype.includes()`
-   Removing padding spaces: `String.prototype.trim()`

### Number ✔️

-   Combining strings and numbers with +
-   Integers vs. Floats
-   Converting strings into Numbers: `parseInt()`, `parseFloat()`
-   Using modulo

### Math ✔️

-   Rounding up with `Math.ceil()`
-   Rounding down with `Math.floor()`
-   Getting random numbers with `Math.random()`
-   Maximum and minimum with `Math.max()`, `Math.min()`

### Number Pitfalls ✔️

-   Dealing with NaN: `isNaN(<expression>)`, `typeof NaN`
-   Very long numbers: `e`, rounding errors
-   Dealing with rounding errors: `Number.prototype.toFixed()`
-   Division pitfalls: Dealing with `Infinity`

### Logical Thinking I ✔️

-   Simple preposition analysis
-   Logical operators: `&&`, `||`
-   Using logic to solve problems; How does a converyor belt work? or How do traffic lights work?

### Boolean ✔️

-   Truthy and falsy values: false, undefined, null, 0, ''
-   Type conversion: `==` vs. `===`
-   Syntax debugging VII: Using assignment (`=`) instead of equality (`===`)
-   Boolean inversion with `!`
-   Short circuit assignment: Assigning variable fallback with `||`

### Array: Saving multiple values in one name ✔️

-   Assigning array literals:

`const <array name> = [<value 1>, <value 2>, ...]`

-   Accessing array items with square brackets
-   Re-assigning array items with square brackets
-   `const`s and array items

### Basic Array methods ✔️

-   Finding Items: `Array.prototype.indexOf(<item>)`
-   Adding items: `Array.prototype.push()`, `Array.prototype.unshift()`
-   Removing items: `Array.prototype.pop()`, `Array.prototype.shift()`
-   Manipulating arrays: `Array.prototype.reverse()`

---

## Programm

### Introduction ✔️

-   The flow of a program (left to right, top to bottom)

### Logical Thinking II ✔️

-   What is an Algorithm?
-   Analyzing problems: Input and Output
-   Coming up with solutions: writing algorithms

### Decisions ✔️

-   Conditional algorithms
-   The conditional statement: `if(<boolean>){ ... }`
-   Syntax debugging VIII: Unclosed curly braces
-   The default case: `else { ... }`
-   Reading a program II (skipping unmet cases)

### Block Scope ✔️

-   Code block definition: `if` example
-   A word on indentation and readability
-   Scope definition: difference between `var`, `let`, `const`
-   When to use: `if` vs. ternary operator

### Multiple choice ✔️

-   Testing multiple conditions: `else if (<boolean>){ ... }`
-   Executing code based on a value: `switch(<expression>){ ... }`
-   When to use: `switch` vs. `else if`

### Numerical Repetition ✔️

-   Repeating code blocks a set number of times:

`for(<initial state>, <end condition>, <step>){ ... }`

-   Breaking out of a loop: `break;`
-   Skipping an iteration: `continue;`
-   Complex iterations: Nesting `for` loops
-   Syntax debugging VIII: Unclosed curly braces (again)

---

## Functions-I

### Introduction ✔️

-   Routines and Subroutines (functions)

### Calling ✔️

-   Review of functions called so far: `console.log()`, `parseInt()`, etc.
-   The call stack (brief introduction)
-   Function arguments

### Declaring ✔️

-   Declaring a function: `function <name>(<parameters>){ ... }`
-   Function parameters: Naming and order
-   Functions declarations as values:

`const <function name> = function(<parameters>){ ... }`

-   Arrow function shorthand:

`const <function name> = (<parameters>) => { ... }`

### Function Scope ✔️

-   Parameters scope
-   Declaring variables in functions
-   Global vs. Local scope: Variable reassignment in functions
-   Reading a program IV (reading functions only when they are called)

### Returns and side effects ✔️

-   Function calls as values: the `return <value>;` statement
-   Side effects definition: Changing the global scope, relying on outer scopes
-   Pure functions definition
-   Reading a program V (Replacing function calls with their return value)
-   Shorter arrow functions:

`const <function name> = (<parameters>) => <return value>`

### Advanced Parameters ✔️

-   Default parameter values:

`function(<parameter> = <default value>) { ... }`

-   Variable number of arguments: Rest params - `...args`
-   Accessing `args` with bracket notation

---

## Data Structur

### Introduction ✔️

-   Variables and relation to memory

### Objects: Saving multiple variables in one namespace ✔️

-   The type of an array: arrays are specific objects, `Array.isArray()`
-   Object literals: Property definition

`const <namespace> = { <key 1>: <value 1>, <key 2>: <value 2>, ... }`

-   Accessing properties with bracket notation (no variables)
-   Accessing properties with dot notation

### Object Scope ✔️

-   Methods definition: Methods are properties with function values
-   Using methods: Review of used methods so far
-   Creating methods
-   Object literal context: methods, `this` and `Function.prototype.bind()`

### Conversion and iterations ✔️

-   Iterating over objects: `for(let <property name> in <object name>){ ... }`
-   Property names to array: `Object.keys(<object>)`
-   Iterating over arrays: `for(let <value name> of <array name>){ ... }`
-   Accessing properties with bracket notation (w. vars)
-   Property values to array: `Object.values(<object>)`

### Clones vs. References⬅️👀

-   Simple values are always clones: String, Number, Boolean
-   Objects are references by default: Array and object literals
-   Shallow cloning objects and arrays: the spread operator `...`
-   Deep cloning objects and arrays: recursive function

### Destructuring

-   Extracting values from arrays: Array destructuring assignment
-   Extracting values from objects: Object destructuring assignment
-   Named function parameters with object destructuring

### Nesting arrays and objects

-   Nesting and accessing arrays within each other
-   Nesting and accessing objects in objects
-   Reading a program VIII (the property chain)
-   Nesting and accessing arrays in objects
-   Nesting and iterating over objects in arrays

### Advanced Array methods

-   Iterating over arrays: `Array.prototype.forEach(<function>)`
-   Converting an array to a different array: `Array.prototype.map(<function>)`
-   Converting an array to a single value: `Array.prototype.reduce(<function>)`
-   Getting a subset of an array: `Array.prototype.filter(<function>)`

### Logical Thinking III

-   Thinking of algorithm complexity: Big O Notation (Very simple introduction)
-   Reading complex algorithm examples: sorting, shortest path
-   Sorting arrays with `Array.prototype.sort(<function>)`

---

## Functions-II

### Closure

-   Declaring functions inside functions
-   Nested scopes: Accessing outer variables
-   First definition of closure: A function that contains at least one variable, and one nested scope
-   Higher Order functions I: Functions that return other functions
-   Reading a program VI (the function call onion)

### Recursive Functions

-   Recursive algorithms
-   Calling a function from within itself
-   Stack overflow: Importance of the exit condition
-   Reading a program VII (recursive call tree)

### Callbacks

-   Higher order functions II: Functions that accept function values (callbacks)

---

## Classes

### Classes: Manufacturing objects with the same structure

-   Creating instances with the `new` keyword, The `Date` class
-   Constructing an object: The `constructor()` method, instance and `this`
-   Prototype methods: Adding custom methods to our class
-   Creating subclasses with `extends` and `super()`
