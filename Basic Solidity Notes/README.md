# Solidity style guide
## [Order of Layout](https://docs.soliditylang.org/en/v0.8.13/style-guide.html#order-of-layout)
### Layout contract elements in the following order:
	1.	Pragma statements
	2.	Import statements
	3.	Interfaces
	4.	Libraries
	5.	Contracts
### Inside each contract, library or interface, use the following order:
	1.	Type declarations
	2.	State variables
	3.	Events
	4.	Modifiers
	5.	Functions
## [Order of Functions](https://docs.soliditylang.org/en/v0.8.13/style-guide.html#order-of-functions)
### Ordering helps readers identify which functions they can call and to find the constructor and fallback definitions easier.
### Functions should be grouped according to their visibility and ordered:
	•	constructor
	•	receive function (if exists)
	•	fallback function (if exists)
	•	external
	•	public
	•	internal
	•	private
### Within a grouping, place the view and pure functions last.
## [NatSpec Format](https://docs.soliditylang.org/en/v0.8.13/natspec-format.html#)
	•	For Solidity you may choose /// for single or multi-line comments, or /** and ending with */.
	
	•	@title Should describe the contract/interface i.e. 
	•	/// @title A simple NFT project
	
	•	@author The name of the author i.e.
	•	/// @author WrappedUsername
	•	
	•	@notice Explains to end user what the object does i.e.
	•	/// @notice Transfers NFT from one account to the other
	
	•	@dev Explains to a developer any extra details i.e.
	•	/** @dev All function calls are currently implemented without known side effects,  
	•	but this may change after further testing/audit process. */
