# mandelbrot

A small Rust program that renders the Mandelbrot set as ASCII art in the terminal.

## How it works

For each character cell, the program maps its position to a point `c` on the
complex plane and iterates `z = z^2 + c` starting from `z = 0`. The number of
iterations before `|z|` exceeds 2 (or `max_iters` is reached) determines which
character is printed, from `' '` (escapes almost immediately) through
`. • * + x $ #` up to `%` (never escapes, i.e. likely in the set).

## Running

```sh
cargo run
```

The viewport and resolution are set in `main()`:

```rust
calculate_mandelbrot(1000, -2.0, 1.0, -1.0, 1.0, 100, 24)
```

Arguments, in order: `max_iters`, `x_min`, `x_max`, `y_min`, `y_max`, `width`, `height`.
