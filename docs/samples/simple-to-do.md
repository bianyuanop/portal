# Simple to-do

## Overview
This example illustrates how to create a simple to-do checklist application. 

The application is built from the following Motoko source code files:

- `Utils.mo`: contains the core functions for adding, completing, and removing to-do checklist items.
- `Types.mo`: contains the type definition of a to-do checklist item.
- `Main.mo`: contains the actor definition and methods exposed by this canister.

This is a Motoko example that does not currently have a Rust variant. 

## Prerequisites
This example requires an installation of:

- [x] Install the [IC SDK](../developer-docs/setup/install/index.mdx).
- [x] Download the following project files from GitHub: https://github.com/dfinity/examples/

Begin by opening a terminal window.

### Step 1: Navigate into the folder containing the project's files and start a local instance of the Internet Computer with the command:

`cd examples/motoko/simple-to-do`
`dfx start --background`

### Step 2: Deploy the canister:

```
dfx deploy
```

### Step 3: Create a to-do checklist by invoking the addTodo method:

```
dfx canister call simple_to_do addTodo '("Create a project")'
dfx canister call simple_to_do addTodo '("Build the project")'
dfx canister call simple_to_do addTodo '("Deploy the project")'
```

### Step 4: Display the to-do checklist by invoking the showTodos method:

```
dfx canister call simple_to_do showTodos
```

### Step 5: Verify the output returns the values you inputted:

```
("
___TO-DOs___
(1) Create a project
(2) Build the project
(3) Deploy the project")
```

### Step 6: Complete a to-do checklist item by invoking the completeTodo method:

`dfx canister call simple_to_do completeTodo '(1)'`

### Step 7: Display the to-do checklist by invoking the showTodos method.

`dfx canister call simple_to_do showTodos`

### Step 8: Verify the return value matches what you would expect.

```
("
___TO-DOs___
(1) Create a project ✔
(2) Build the project
(3) Deploy the project")
```