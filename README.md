## :wrench: Monty Opcodes

* **push**
  * Usage: `push <int>`
  * Pushes an element to the stack.
  * The parameter `<int>` must be an integer.

* **pall**
  * Prints all values in the stack/queue, startin\
g from the top.
* **pint**
  * Prints the top value of the stack/queue.

* **pop**
  * Removes the top element of the stack/queue.

* **swap**
  * Swaps the top two elements of the stack/queue\
.
* **nop**
  * Does not do anything.

* **add**
  * Adds the top two elements of the stack/queue.
  * The result is stored in the second element fr\
om the top and the top element is popped.
* **sub**
  * Subtracts the top element of the stack/queue \
from the second element from the top.
  * The result is stored in the second element fr\
om the top and the top element is removed.

* **mul**
  * Multiplies the top two elements of the stack/\
queue.
  * The result is stored in the second element fr\
om the top and the top element is removed.
* **div**
  * Divides the second element from the top of th\
e stack/queue by the top element.
  * The result is stored in the second element fr\
om the top and the top element is removed.

* **mod**
  * Computes the modulus of the second element fr\
om the top of the stack/queue divided by the top \
element.
  * The result is stored in the second element fr\
om the top and the top element is removed.
* **pstr**
  * Prints the string contained in the stack/queu\
e.
  * Prints characters element by element until th\
e stack/queue is empty, a value is `0`, or an err\
or occurs.

* **rotl**
  * Rotates the top element of the stack/queue to\
 the bottom.
 * **rotr**
  * Rotates the bottom element of the stack/queue\
 to the top.

* **stack**
  * Switches a queue to stack mode.

* **queue**
  * Switches a stack to queue mode.
  :arrow_forward: Opcodes preceeded by a `#` are tr\
eated as comments and the corresponding line is i\
gnored.

:arrow_forward: Lines can be empty and can contai\
n any number of spaces before or after an opcode \
and its argument (only the first opcode and/or ar\
gument is taken into account).
## :clipboard: Examples

Note, Monty Interpreter runs in the default mode \
of STACK mode. Meaning it uses a stack. To switch\
 to queue mode, see examples below.

Push values onto the stack and print them all, or\
 the top of the stack/front of queue.
 ```
$ cat push_pall_pint.m
push 1
push 2
push 3
pall
pint
$ ./monty push_pall_pint.m
3
2
1
3
```
Using mathmatical operations to add, multiply, di\
vide, etc. Takes the second from the top and perf\
orms the operation on the top: `second_from_top /\
 top`, `second_from_top - top`, `etc`. Then assig\
ns that to the `second_from_top` and pops the top\
 element off the stack.
 $ cat math.m
push 3
push 2
push 1
pall
mul
pall
$ ./monty math.m
1
2
3
1
6
```
Entering queue mode to perform all operations in \
FIFO (queue) mode instead of default LIFO (stack)\
 mode. Note: does not change current stack, sets \
front of queue to top of stack.

```
$ cat queue.m
queue
push 1
push 2
push 3
pall
stack
push 4
push 5
push 6
pall
$ ./monty queue.m
1
2
3
6
5
4
1
2
3
```
## :blue_book: Authors

* **Ruth Mayenga** - [@mlle-kwamboka](https://gi\
thub.com/mlle-kwamboka)

* **Olare Odhiambo** - [@Olare](https://git\
hub.com/Mr.Olare)# monty
