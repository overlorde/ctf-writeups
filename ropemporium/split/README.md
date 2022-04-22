First i found out for what cyclic() value the exec gets core dumped.

Then I found out the offset from the cyclic by finding out what rsp hold when i had this core dumped.

Then I used rabin -Z split to find out the "/bin/cat flag.txt" string inside the binary.

Then found out the system address with elf.symbols.system and used one ROP gadget pop rdi, ret.

What it does?

At first we overwrite the eip with the gadget address. That means, pwnme's return address gets overwritten by this
gadgets starting address.
pop rdi pops whatever is in stack and keeps it in rdi. We know in 64 bit we use rdi as an argument. We can also see it in the usefulFunction disassembly.

Then what we do is, we overwrite the return address of the gadget with system.plt address.

And thus we find our flag.
