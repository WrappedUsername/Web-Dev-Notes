## Understanding String Immutability

In JavaScript, string values are immutable, which means that they cannot be altered once created.

For example, the following code:

```JavaScript
let myString = "Bob";
myString[0] = "J";
```
cannot change the value of myString to Job, because the contents of myString cannot be altered. Note that this does not mean that myString cannot be changed, just that the individual characters of a string literal cannot be changed. The only way to change myString would be to assign it with a new string, like this:
```JavaScript
let myStr = "Bob";
myStr = "Job";
```

## Using bracket notation, finding characters in a string.
Bracket notation is a way to get a character at a specific index within a string.
Most modern programming languages, like JavaScript, don't start counting at 1 like humans do. They start at 0. This is referred to as Zero-based indexing.

For example, the character at index 0 in the word Charles is C. So if const firstName = "Charles", you can get the value of the first letter of the string by using firstName[0]

for example:
```JavaScript
const firstName = "Charles";
const firstLetter = firstName[0];
```
firstLetter would have a Nth value of the string C.

## Nth - Using bracket notation to get the Nth character in a string.

Nth is a naming convention that describes the position of a character in a string. Nth can represent any position of a character in a string.

For example:
```JavaScript
const firstName = "Ada";
const secondLetterOfFirstName = firstName[1];
```
secondLetterOfFirstName would have a Nth value of the string d.

In order to get the last letter of a string, you can subtract one from the string's length.

For example:
```JavaScript
const firstName = "Ada";
const lastLetter = firstName[firstName.length - 1];
```
lastLetter would have a Nth value of the string a.

Use the same principle to retrieve the last character in a string to retrieve the Nth-to-last character.

For example:
```JavaScript
const firstName = "Augusta";
const thirdToLastLetter = firstName[firstName.length - 3];
```
thirdToLastLetter would have a Nth value of the string s.





