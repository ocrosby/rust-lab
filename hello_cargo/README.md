# Hello Cargo

One of my first rust programs.

## Generating the new hello_cargo project

```shell
cargo new hello_cargo
cd hello_cargo
```

## Building the project

```shell
cargo build
```

Because the default build is a debug build, Cargo puts the binary in the directory named debug. You can run the executable as follows. Running `cargo build` for the first time also causes Cargo to create a new file at the top level: `Cargo.lock`. This file keeps track of the exact versions fo dependencies in your project.

We can also use `cargo run` to compile the code and then run the resultant executable all in one command.

```shell
cargo run
```

## Run the debug version of the programs

```shell
./target/debug/hello_cargo
```

## Cleaning up after a build

```shell
cargo clean
```

## Check to make sure it compiles but doesn't produce an executable.

```shell
cargo check
```

## Building a release version

```shell
cargo build --release
```

