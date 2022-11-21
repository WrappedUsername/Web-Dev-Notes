# The Ethereum Virtual Machine - 🚧 Work in Progress 🏗

<p align="left"> <img src="https://komarev.com/ghpvc/?username=TheEthereumVirtualMachine&label=Repository%20views&color=0e75b6&style=flat" alt="wrappedusername" /> </p>

```yml
How the world's decentralized computer works:
```

- The EVM (Ethereum Virtual Machine) is very similar to a virtual machine on your personal computer,
  - in that it is software imitating, actual dedicated hardware, but in reality,
  
## 💻 The host machine must share  
  - a virtual machine is simply sharing the host computer's dedicated hardware,
    - a virtual machine is allocated certain amounts of usage, usually a percentage of that particular resource,
    
```yml
Each image of a virtual machine has:
```

- CPU
- RAM
- Storage
- and a Network Interface

## 🌐 The World's 💻 Computer Parts

```yml
The EVM has:
```

- CPU: each [ethereum node](https://etherscan.io/nodetracker) is able to be run on a computer with the specs of a nice gaming PC, but without the GPU.
  - At the time of writing there was around,
  
| [7,500 ethereum nodes](https://etherscan.io/nodetracker) | 
| :---: | 
  
  - The ethereum nodes use an Execution Client with the [Instruction Set](https://github.com/ethereumbook/ethereumbook/blob/develop/13evm.asciidoc#the-evm-instruction-set-bytecode-operations), [Inline Assembly](https://docs.soliditylang.org/en/latest/assembly.html), and Solidity comprised of basic static data types ( booleans, integers, addresses, etc.) to come to, a consensus as to how, and what to change in the [ethereum world state](https://github.com/ethereumbook/ethereumbook/blob/develop/13evm.asciidoc#ethereum-state).
  - Each node must run both a consensus client, and an execution client.
  - [All nodes must come to consensus](https://github.com/ethereumbook/ethereumbook/blob/develop/14consensus.asciidoc#consensus), 

## 🗜 Setting limits

```yml
The EVM is a quasi–Turing-complete state machine: 
```
 
- "quasi" because all execution processes are limited to a finite number of computational steps by the amount of gas available for any given smart contract execution.
  - [Gas](https://github.com/ethereumbook/ethereumbook/blob/develop/13evm.asciidoc#gas) is used to solve the [Turing complete state, halting problem](https://github.com/ethereumbook/ethereumbook/blob/develop/13evm.asciidoc#turing-completeness-and-gas),
- As such, the halting problem is "solved" (all program executions will halt) and the situation where execution might (accidentally or maliciously) run forever, thus bringing the Ethereum platform to halt in its entirety, is avoided.

## 📚 The stack

```yml
The EVM has a stack-based architecture, storing all in-memory values on a stack:
```

- It has a maximum size of 1024 elements and contains words of 256 bits.
- It works with a word size of 256 bits (mainly to facilitate native hashing and elliptic curve operations) and has several addressable data components.
  - An immutable program code ROM, loaded with the bytecode of the smart contract to be executed
  - A volatile memory, with every location explicitly initialized to zero
  - A permanent storage that is part of the Ethereum state, also zero-initialized
- There is also a set of environment variables and data that is available during execution.

```yml
Access to the stack is limited to the top end in the following way:
```
- It is possible to copy one of the topmost 16 elements to the top of the stack or swap the topmost element with one of the 16 elements below it.
- All other operations take the topmost two (or one, or more, depending on the operation) elements from the stack and push the result onto the stack.
- Of course it is possible to move stack elements to storage or memory in order to get deeper access to the stack, but it is not possible to just access arbitrary elements deeper in the stack without first removing the top of the stack.
- Calls are limited to a depth of 1024, which means that for more complex operations, loops should be preferred over recursive calls. 
- Furthermore, only 63/64th of the gas can be forwarded in a message call, which causes a depth limit of a little less than 1000 in practice.

## 🗄 Data Storage
  
```yml
The Ethereum Virtual Machine has three areas where it can store data: 
- storage, 
- memory, 
- and the stack
```

- RAM 
  - Memory is a freshly cleared instance for each message call,
  - and it is linear, and can be addressed at the byte level, but reads are limited to a width of 256 bits, while writes can be either 8 bits or 256 bits wide.
  - Memory is more costly the larger it grows, because (it scales quadratically), and
  - memory is expanded by a word (256-bit), when accessing (either reading or writing) a previously untouched memory word (i.e. any offset within a word).
  - At the time of expansion, the cost in gas must be paid ( and remember it scales quadratically).
- Storage

## 📡 The EVM Network 

- The Network Interface
  - An RPC (remote procedure call) endpoint is like a node's address: it's a URL which requests for blockchain data can be sent to. 
  - The Ethereum JSON-RPC spec defines the methods which you can use to retrieve data from a node.

