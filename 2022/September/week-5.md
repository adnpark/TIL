### Mon, Sep 26

- Tried to solve 2 ethernaut levels, but failed both. Will try tomorrow again.
- Learned the under the hood of EVM, how EVM bytecode is created, opcodes works.
- fallback function cannot return any values.
- view function is cannot be used for the reentrancy attack, since it is simply cannot modify any storage values.

### Tue~Wed, Sep 27~28

- Solved one Ethernaut stage: Shop. I've missed the point, but could solve it with other creative way. Learned a lot from it.
- Learned that maxFeePerGas is not sum of maxPriorityFeePerGas and BaseFeePerGas.
  - maxFeePerGas is maximum gas price can be applied to transaction.
  - maxPriorityFeePerGas is maximum gas price can be paid to validators.
  - BaseFeePerGas is literally base fee for the network itself
  - PriorityFee can be paid from (maxFeePerGas - BaseFeePerGas), and it cannot be greater than maxPriorityFeePerGas.
  - So technically, (BaseFeePerGas + maxPriorityFeePerGas) can be greater than maxFeePerGas.
- Learned that default getFeeData api of provider in Polygon network is not working properly. It returns very low level of fee data resulting in failure of transaction with 'transaction underpriced'.

### Thu, Sep 29

- Solved Etheranut stage: Denial. Could solve with simple reentrancy trick. Good chance to remind me of transfer, send, call methods and its caveats.
- Learned various methods of Object. Seems to be good to get used to using functional programming style.

### Fri, Sep 30

- Learned how to use Jest test suite. Learned how to mocking modules, functions. spyOn() method is just awesome, it helps to mock function result in unit of single action.
- Made a PR for fixing gas related issues. Learned that most of transaction failures are caused by gas issues.
- Tried to solve Ethernaut: Dex, but failed. I'll try it tomorrow again. It'd be better to run in local environment for getting feedback quickly.
