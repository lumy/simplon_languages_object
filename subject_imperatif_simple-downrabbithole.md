
# Down the rabbit hole

You were having a nap in the garden, when suddenly you hear a rabbit shouting 'Late, I'm Late !'.
You felt his distress and ask him if he wanted some help.
The rabbit, still in the rush, tells you: "I have instruction but i can't understand them, the queen
gave me a code but i don't understand it."

## programme

The rabbit always start at position (0, 0) (and he's facing north), the position can be positive or negative.
Given some instruction you will have to calculate the position for the rabbit.

eg.

`right right left left front halfturn front`

```
# received, 'front left right': 0.0 -> 0.1 -> -1,1, -1,2
|-1,1 |0,1 |1,1 |
|-1,0 |0, 0|1,0 |
|-1,-1|0,-1|1,-1|
```

Your programme will receive instruction from standart input or from arguments and print the position
where the bunny has to be.

```bash
$ cat myfile
left right left
$ ./rhole myfile
-2,2
$ ./rhole
Instruction: left right left
-2,2
```
