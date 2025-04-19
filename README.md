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
