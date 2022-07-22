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
