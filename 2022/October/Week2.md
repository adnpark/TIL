### Summary

### Week 1, Oct

- had coll down period at work and destressed myself.

## Week 2, Oct

### Tue 11

- learned how to improve simple for loop to pipeline functions

### Wed 12

- Designed new architecture for contract and api server at work.
- Always keep in mind separation of concerns.

### Thu 13

- learned that time complexity of O(n) should be avoided in smart contract implementation. It can potentially halt part of contract execution with `Exceeds block gas limit` error.
- Published [blog post](https://medium.com/@aiden.p/%EC%8A%A4%EB%A7%88%ED%8A%B8-%EC%BB%A8%ED%8A%B8%EB%9E%99%ED%8A%B8%EC%97%90%EC%84%9C-o-n-%EC%9D%84-%ED%94%BC%ED%95%98%EA%B3%A0-o-1-%EC%9D%84-%EC%A7%80%ED%96%A5%ED%95%B4%EC%95%BC-%ED%95%98%EB%8A%94-%EC%A7%84%EC%A7%9C-%EC%9D%B4%EC%9C%A0-74b867b2281e) with this issue in Korean.

## Week 3, Oct

### Mon 17

- Implemented ERC20 token minter contract and wrote test cases along with it.
- Reminded the concept of dependency cycle and how to avoid it in smart contract development.
- Always better to avoid tightly coupled system.

### Tue 18

- Implemented treasury contract that can hold and transfer ERC20 tokens.
- Learned how typeDi works and dependency injection.
- Learned SOLID principle of OOP.
  - Single Responsibility(SRP): Every class must have single responsibility(Simply, single feature). If you have to modify a class, then you must have single reason.
  - Open/Closed(OCP): should be open for extension and closed for modification. -> It should edit or add features without modification.
  - Liskov substitution(LSP): Parent object can be substituted to child object. (?)
  - Interface segregation(ISP): Client should depend on its own methods. Class should not implement interface will not be used.
  - Dependency inversion(DIP): Depend upon abstractions(cannot be changed easily), not concretions(can be easily changed).
- Learned inversion of control(IoC): In IoC, custom-written portions of a computer program receive the flow of control from a generic framework.
  - DI(Dependency Injection) is one of measures to achieve IoC.

### Wed 19

- Created PR for new contracts and test cases.
- Read [Aave-Certora-Secureum: A DeFi Security Collaboration](https://secureum.substack.com/p/aave-certora-secureum-collaboration)
- Read part of [Solidity 101](https://secureum.substack.com/p/solidity-101)

### Thu 20

- Tried to solve Secureum RACE-10 problem sets. Only got 4 out of 8. It's not that bad actually, I'll make a note for RACE-10 and publish it in Korean and English.
- Read part of [Solidity 101](https://secureum.substack.com/p/solidity-101)
  - NatSpec: Ethereum Natural Language Specification Format. It is recommended that Solidity contracts are fully annotated using NatSpec for all public interfaces (everything in the ABI).
    - @notice is for end users.
    - @dev is for developer any extra details.
  - State Variables: Constant & Immutable
    - `constant`
      - the value has to be fixed at compile-time
      - cannot access storage, blockchain data(e.g block.timestamp, address(this).balance), or execution data (msg.value, or gasleft())
      - cannot make call to external contract
    - `immutable`
      - can still be assigned at construction time i.e in the constructor or point of declaration.
      - can be assigned only once
    - _The compiler does not reserve a storage slot for these variables, and every occurrence is replaced by the respective value._ (???)
  -

### Fri 21

- Read part of [Solidity 101](https://secureum.substack.com/p/solidity-101)
  - Function Modifiers
    - The function’s control flow continues after the `_` in the preceding modifier.
    - Expression of the modifier after `_` is executed after function body executed.
    - The `_` symbol can appear in the modifier multiple times. Each occurrence is replaced with the function body.
  - Function Mutability Specifiers: Functions can be specified as being `pure` or `view`:
    - view functions can read contract state but cannot modify it. This is enforced at runtime via `STATICCALL` opcode.
    - The following are considered state modifying:
      - 1. Writing to state variables
      - 2. Emitting events
      - 3. Creating other contracts
      - 4. Using selfdestruct
      - 5. Sending Ether via calls
      - 6. Calling any function not marked view or pure
      - 7. Using low-level calls
      - 8. Using inline assembly that contains certain opcodes.
    - The following are considered reading from state:
      - 1. Reading from state variables
      - 2. Accessing address(this).balance or <address>.balance
      - 3. Accessing any of the members of block, tx, msg (with the exception of msg.sig and msg.data)
      - 4. Calling any function not marked pure
      - 5. Using inline assembly that contains certain opcodes.
  - It is not possible to prevent functions from reading the state at the level of the EVM.
    - It is only possible to prevent them from writing to the state via STATICCALL. **Therefore, only view can be enforced at the EVM level, but not pure.**

### Mon 24

- Learned that cannot reuse unpublished version of npm packages.
  - `package-name@version is unique, and cannot be reused by unpublishing and re-publishing it. We recommend publishing a minor version update instead.`
