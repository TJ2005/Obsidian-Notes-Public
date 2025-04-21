## Endianness

### History
This word is derived from the word gulliver travels. In the story there was a Quarrel over the breaking of eggs via which end? the ones who broke the egg with the little end were called little endians and the one who broke ethe egg from the big end were called big endians.
![[Pasted image 20240722104227.png]] 

### How we stumbled upon this creation
Now in computers whenever there is a multibyte data for example `0xa011833d1`
The question was how do we represent the data in a register?
Do we put the most significant bit first or the least significant byte first?

The most significant byte in lets say 512 is 5 which stands for the hundredth position and 2 is the least significant. In the multibyte data on the example above the most significant byte is `0xa011833d1`.  Humans write numbers in MSB first that is Big Endian. 

Endianness Strictly talks about re ordering [[Bytes]] and not [[Bits]]. Bits are 4 bytes together. Bytes is one binary digit alone.

According to [[Internet Standards]] and [[RFC 793]] all the fields in network header must be in [[Big Endian]]. Thus conversion is needed when the computers are mismatched.
##### MSB 
Most significant Byte is the one that is in the highest power for lets say in 512 it is 5 for 500 and for `0xa011833d1` it is 01
##### LSB
Least Significant byte is the one that is in the lowest power for lets say in 512 in 2 in units position and for `0xa011833d1` in its 1 as well.
Refer [Youtube](https://www.youtube.com/watch?v=LxvFb63OOs8)
![[Pasted image 20240722110037.png]]

#### Why even Study Endianness?
When inspecting in debuggers if for example in little endianness the bytes will be stored in a reverse order. When u manually call the address register and check the one **BIT** (NOT BYTE) the hardware does the endian swap for us. But when we call a single digit we might not recognize. 

There's an even bigger problem though. Imagine if in this depiction of memory register we call first two memory addresses first and last two last. This way u get ccdd and aabb this order is completely jumbled up even after endian swap from hardware. 
![[Pasted image 20240726003037.png]]



### Little Endian
In little-endian format, the least significant byte (LSB) is stored first, at the lowest memory address. For example, the 32-bit hexadecimal number 0x12345678 would be stored as:
- Address 0: 0x78
- Address 1: 0x56
- Address 2: 0x34
- Address 3: 0x12

### Big Endian
In big-endian format, the most significant byte (MSB) is stored first, at the lowest memory address. For example, the 32-bit hexadecimal number 0x12345678 would be stored as:
- Address 0: 0x12
- Address 1: 0x34
- Address 2: 0x56
- Address 3: 0x78


### Conversion of Little Endian to Big Endian
To convert a little-endian number to big-endian, you reverse the order of the bytes. For example, to convert the 32-bit number 0x12345678 from little-endian to big-endian:

- Little-endian: 78 56 34 12
- Big-endian: 12 34 56 78

You can perform this conversion programmatically by swapping the byte positions.

---