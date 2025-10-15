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
- the naming convention for constants is to use all uppercase with underscores between wordsj


```rust:
// Declaring constants

const THREE_HOURS_IN_SECONDS: u32 = 60 * 60 * 3;
```

#### Shadowing

You can declare a new variable with the same name as a previous variable. Rustaceans say that the first variable is shadowed by the second, which means that the second variable is what the compiler will see when you use the name of the variable.


```rust
fn main() {
    let x = 5;

    let x = x + 1;

    {
        let x = x * 2;
        println!("The value of x in the inner scope is: {x}");
    }

    println!("The value of x is: {x}");
}
```

- we can change the tope of the value but reuse the same name with shadowing

```rust
let spaces = "     ";
let spaces = spaces.len();
```

## Data Types

- every value in Rust is of a certain data type
- there are two data type subsets: scalar and compound



Note: Rust is a statically typed language, which means that it must know the types of all variables at compile time.

- the compiler can usually infer what type we want to use base don the value and how we use it
- when many types are possible we must add a type annotation

```rust
let guess: u32 = "42".parse().expect("Not a number!");
```

### Scalar Types

Scalar Type
: a scalar type represents a single value

Four primary scalar types

- integers
- floating point numbers
- Booleans
- characters

#### Integer Types

Integer
: an integer is a number wihtout a fractional component

The `u32` type declaration indicates that the value it's associated with should be 
an unsigned integer that takes up 32 bits of space.

- signed integer types start with i instead of u

Integer Types in Rust

- i8 (8-bit signed integer)
- u8 (8-bit unsigned integer)
- i16 (16-bit signed integer)
- u16 (16-bit unsigned integer)
- i32 (32-bit signed integer)
- u32 (32-bit unsigned integer)
- i64 (64-bit signed integer)
- u64 (64-bit unsigned integer)
- i128 (128-bit signed integer)
- u128 (128-bit unsigned integer)
- isize (arch signed integer)
- usize (arch unsigned integer)


Signed numbers ares tored using two's compliment representation.

Each signed variant can store numbers from -(2^(n-1)) to 2^(n-1)-1 inclusive so an i8 can store numbers from
-(2^7) to 2^7-1, which equals -128 to 127.

`isize` and `usize` types depend on the archtecture of the computer your program is running on or targeted for.


