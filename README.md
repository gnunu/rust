# rust

int types:
i8, u8
i16, u16
i32, u32
i64, u64
i128, u128
isize, usize

float types:
let x = 2.0; // f64, default
let y: f32 = 3.0; // f32

let f: bool = false;

Rust’s char type is four bytes in size and represents a Unicode Scalar Value.
Unicode Scalar Values range from U+0000 to U+D7FF and U+E000 to U+10FFFF inclusive.
let c = 'z';

tuple:
let tup: (i32, f64, u8) = (500, 6.4, 1);
let (x, y, z) = tup; // destructuring
let x = tup.0;

module system:
Package: Cargo.toml, 0-1 library
Crate: binary or library, crate root (of module tree), src/bin
Module: tree
Path

blanket implementations:
impl<T: Display> ToString for T {
    // --snip--
}
use:
let s = 3.to_string();

lifetime elision rules:
input lifetimes
output lifetimes
1) each parameter that is a reference gets its own life- time parameter.
2) if there is exactly one input lifetime parameter, that lifetime is assigned to all output lifetime parameters.
3) the lifetime of self is assigned to all output lifetime parameters.

test control:
$ cargo test -- --test-threads=1 --nocapture --ignored

test attributes:
#[cfg(test)] // not included on cargo build
#[test]
#[ignore]
#[should_panic(expected = "prefix")]

integration test:
tests/integration_test.rs
tests/common/mod.rs
    Files in subdirectories of the tests directory don’t get compiled as separate crates or have sections in the test output.

project:
cargo new rt

closure:
All closures implement at least one of the traits: Fn (read env only ), FnMut (mutate env), or FnOnce (move).
When a closure captures a value from its environment, it uses memory to store the values for use in the closure body.
memoization/lazy evaluation

iterator:
into_iter: returns owned values
iter_mut: iterate over mutable references

Cargo.toml:
[profile.dev]
opt-level = 0

[profile.release]
opt-level = 3

