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

```yml
The EVM has:
```

- CPU
  - The Instruction Set uses basic data types ( booleans, integers, addresses, etc.) to come to, a consensus as to how, and what the world's CPU computes.
  
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
- and a Network Interface

