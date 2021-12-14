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
