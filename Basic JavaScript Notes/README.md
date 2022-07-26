# Basic JavaScript Notes
<p align="left"> <img src="https://komarev.com/ghpvc/?username=BasicJavaScriptNotes&label=Repository%20views&color=0e75b6&style=flat" alt="wrappedusername" /> </p>

### Find remainder operator %
```JavaScript
/** 
@notice myVariable is assigned a value of 2, because 3 will go into 11, 
3 times with a remainder of 2. 
*/
const myVariable = 11 % 3; 
```
### Increment ++ Decrement --
```JavaScript
myVariable++;
myVariable--;
```

- another example would be,

```JavaScript
    for (let i = 0; i < n; i++) {   // <------- increment used here a lot!
        if (arr[i] > 0 ) {
            positive += 1; 
        } else if (arr[i] < 0 ) {
            negative += 1; 
        } else {
            zero += 1; 
        }
    }
```

## Compound assignments += -= *= /= 
```JavaScript
/// @notice augmented addition
const myVariable += 2;
/// @notice augmented subtraction
const myVariable -= 2;
/// @notice augmented multiplication
const myVariable *= 2;
/// @notice augmented division
const myVariable /= 2;
```

- another example would be,

```JavaScript
    for (let i = 0; i < n; i++) {
        if (arr[i] > 0 ) {
            positive += 1; // <------- augmented addition
        } else if (arr[i] < 0 ) {
            negative += 1; // <------- augmented addition
        } else {
            zero += 1; // <------- augmented addition
        }
    }
```

## Escaping literal quotes \ before "
```JavaScript
const myVariable = 'backslash before, let\'s use "quotation marks" inside a string.';
```
## Single quotation marks ' vs. double "
```JavaScript
/** 
@notice When using both single and double quotation marks 
inside a string one must use the proper escape sequence, because if you have that same quotation mark 
somewhere in the middle, the string will stop early and throw an error.   
*/
const myVariable = 'backslash before, let\'s use "quotation marks" inside a string.';
/// @notice The use of single quotation marks allows the proper use of double quotation marks inside the string.
const myVariable = '<a href="http://www.example.com" target="_blank">Link</a>';
```
## Escape sequences 
| Command | Description |
| --- | --- |
|  \\' | Single Quotation Mark |
| \\" | Double Quotation Mark |
| \\\ | Backslash |
| \\n | New Line |
| \\r | Carriage Return |
| \\t | Tab |
| \\b | Word Boundry |
| \\f | Form Feed |
```JavaScript
const myString = "FirstLine\n\t\\SecondLine\nThirdLine";
console.log(myString); 
/** @notice output:
FirstLine
	\SecondLine
ThirdLine
*/
```
## Concatenating strings.
```JavaScript 
/** 
@notice Use the += operator to concatenate a string onto the end of an existing string variable. 
This can be very helpful to break a long string over several lines. 
*/
/// @notice Concatenation does not add spaces between concatenated strings, so you'll need to add them yourself.
let myVariable = "This is the first sentence. "; 
myVariable += "This is the second sentence.";
```
## Constructing strings with variables.
```JavaScript
/** @notice By using the concatenation operator + you can insert one or more 
variables into a string you're building.
*/
const myName = "WrappedUsername";
let myVariable = "Hellos my name is " + myName + ", how are you?";
```
## Appending variables to strings.
```JavaScript
/// @notice Appending variables to a string using the plus equals += operator.
const someAdjective = "interesting!";
let myVariable = "Learning to code is ";
myVariable += someAdjective;
```
## Find the length of a string.
```JavaScript
/// @notice Find the length of a String value by writing .length after the string variable or string literal.
let myNameLength = 0;
const myName = "WrappedUsername";
console.log(myName.length);
myNameLength = myName.length;
```





