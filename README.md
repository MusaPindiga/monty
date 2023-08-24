# Monty Stack and Queue Operations Implementation

This repository provides an implementation of stack and queue operations in C programming language based on the Monty language specifications.

## Introduction

The Monty language is a scripting language that uses opcode instructions to manipulate a stack of integers. This implementation utilizes two main structures: `instruction_t` to map Monty opcodes to corresponding C functions and `stack_t` to create a doubly linked list representing the stack (or queue).

## Structures

### `instruction_t`

- `char *opcode`: A string representing a Monty opcode.
- `void (*f)(stack_t **stack, unsigned int line_number)`: A function pointer that points to a C function corresponding to the Monty opcode.

### `stack_t`

- `int n`: An integer value stored in the node.
- `struct stack_s *prev`: A pointer to the previous node in the stack (or queue).
- `struct stack_s *next`: A pointer to the next node in the stack (or queue).

## Instructions

This implementation provides the following main operations:

- `push`: Add a new node with a given integer value to the stack.
- `pop`: Remove the top node from the stack.
- `pint`: Print the value at the top of the stack without removing it.
- `swap`: Swap the top two elements of the stack.
- `add`: Add the top two elements of the stack and replace them with the result.
- `nop`: No operation (used for comments).

## Usage

1. Clone the repository:

   ```
   git clone https://github.com/MusaPindiga/monty.git
   cd monty
   ```

2. Compile the C program:

   ```
   gcc -Wall -Werror -Wextra -pedantic *.c -o monty
   ```

2. Run the Monty interpreter:

   ```
   ./monty example.m
   ```

## Example

Suppose you have a Monty bytecode file named `example.m` with the following contents:

```
push 1
push 2
push 3
pint
pop
```

Running the interpreter as mentioned above would produce:

```
3
2
```
