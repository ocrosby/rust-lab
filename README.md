# rust-lab

My rust lab project.

## Using cargo to create a new rust project

```shell
cargo new hello_cargo
cd hello_cargo
```

## Common Programming Concepts

- variables
- basic types
- functions
- comments
- control flow

### Variables and Mutability

By default, variables are immutable. However, you still have the option to make
your variables mutable.

When a variable is immutable, once a value is bound to a name, you can't change
that value.

```rust
fn main() {
    let x = 5;
    println!("The value of x is: {x}");
    x = 6;
    println!("The value of x is: {x}");
}
```

When you save and run the program using `cargo run` you should receive an error
message regarding an immutability error.

Now if you change the let declaration/assignment

```rust:
fn main() {
    let mut x = 5;
    println!("The value of x is: {x}");
    x = 6;
    println!("The value of x is: {x}");
}
```

Now executing this program using `cargo run` you will notice that you no longer
receive the error. This is because we've made the value of x mutable.

#### Constants

Constant
: constants are values that are bound to name and are not allowed to change

- you are not allowed to use `mut` with constants
- constants aren't just mutable by default -- they are always immutable
- constants can be declared in any scope including the global scope
- constants may be set only to a constant expression, not the result of a value that could only be computed at runtime

```rust:
// Declaring constants

const THREE_HOURS_IN_SECONDS: u32 = 60 * 60 * 3;
```




