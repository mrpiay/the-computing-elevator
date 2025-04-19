The **Computing Elevator** is a unique and engaging web-based educational tool designed to introduce the basics of computer architecture and programming logic through a visual and interactive experience.

The simulator represents a minimal computer architecture illustrated as **twin towers** (representing the memory) connected by an **elevator** (representing the CPU).

- A **program** consists of instructions and data written on the corresponding floors.
- The **CPU** is visualized as an elevator moving between floors, following the **fetch-decode-execute** cycle.
- The elevator displays the value of the **accumulator** register (ACC) as each instruction is processed.
- Programs always start at instruction floor **0** and proceed **sequentially** unless a jump instruction is found.
- The internal **program counter** (PC) is updated automatically and indicates the next instruction floor where the elevator will stop.
- In addition to **direct addressing** mode, where instructions directly reference a specific data floor, **indexed addressing** is also supported. Instructions in the format **7X** perform the same operation as instructions in the format **0X**, but the data floor is calculated as **X + Data[9]**. If data floor 9 (the **index register**) is 0 or empty, the instruction **7X** behaves as instruction **7** (see Example 11).

The Computing Elevator supports instructions encoded with one or two denary digits, as defined in its **Instruction Set**, emulating a machine code programming language. With only 10 instruction and data floors available, it encourages users to get creative, designing their own problems and solving them efficiently, like generating a full Fibonacci sequence in just 9 instructions (see Example 10).

Users can design their own programs by entering instructions and data on the respective floors. These programs can be **saved** to a JSON file and **loaded** later, facilitating sharing and experimentation.


## Instruction Set

### Memory & Arithmetic

| Code | Instruction       | Description                                                      |
|------|-------------------|------------------------------------------------------------------|
| 0X   | ACC ← DATA[X]     | Copy the value stored on data floor X into the elevator          |
| 1X   | ACC ← ACC + DATA[X] | Add the value stored on data floor X to the elevator            |
| 2X   | ACC ← ACC - DATA[X] | Subtract the value stored on data floor X from the elevator    |
| 3X   | X ← ACC           | Copy the value from the elevator into data floor X               |
| 7X   | ACC ← DATA[X + DATA[9]] | Copy the value stored on data floor (X + DATA[9]) into the elevator (indexed addressing) |

### Program Flow

| Code | Instruction               | Description                                                  |
|------|---------------------------|--------------------------------------------------------------|
| 4X   | PC ← X                    | Go to instruction floor X                                     |
| 5X   | IF ACC == 0 THEN PC ← X  | If the elevator value is 0, go to instruction floor X        |
| 6X   | IF ACC < 0 THEN PC ← X   | If the elevator value is less than 0, go to instruction floor X |

### Input/Output

| Code | Instruction       | Description                                      |
|------|-------------------|--------------------------------------------------|
| 7    | ACC ← INPUT       | Copy the value entered by the user into the elevator |
| 8    | OUTPUT ← ACC      | Copy the value from the elevator into the output |
| 9    | STOP              | Stop the program                                |
