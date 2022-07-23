## Compound assignments += -= *= /= e.g. JavaScript, Solidity etc.
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
## Escaping literal quotes \ before " e.g. JavaScript, Solidity etc.
```JavaScript
const myVariable = 'backslash before, let\'s use "quotation marks" inside a string.';
```
## Single quotation marks ' vs. double " e.g. JavaScript, Solidity etc.
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
## Concatenating strings e.g. JavaScript.
```JavaScript 
/** 
@notice Use the += operator to concatenate a string onto the end of an existing string variable. 
This can be very helpful to break a long string over several lines. 
*/
/// @notice Concatenation does not add spaces between concatenated strings, so you'll need to add them yourself.
const myVariable = "This is the first sentence. "; 
myVariable += "This is the second sentence.";
```
## Constructing strings with variables e.g. JavaScript.
```JavaScript
/** @notice By using the concatenation operator (+), you can insert one or more 
variables into a string you're building.
*/
const myName = "WrappedUsername";
const myVariable = "Hellos my name is " + myName + ", how are you?";
```

