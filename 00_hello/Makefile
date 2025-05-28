# Makefile for compiling and running main.rs

# Name of the Rust file (without extension)
TARGET = main

# Rust compiler
RUSTC = rustc

.PHONY: all run clean

# Default target: compile the program
all: $(TARGET)

$(TARGET): $(TARGET).rs
	$(RUSTC) $(TARGET).rs -o $(TARGET)

# Run the compiled binary
run: all
	./$(TARGET)

# Clean up compiled binary
clean:
	rm -f $(TARGET)
