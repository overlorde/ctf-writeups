
## ret2win solution

We can see with A*40 and B*6 overwrites the ret address of pwnme function call stack.

We know when the return address pops it will successfully overwrite the RIP register.

Thus, RIP will point to ret2win function.
