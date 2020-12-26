```rust
let result = "Hello, world!".as_bytes();

println!("{:?}", std::str::from_utf8(&result).unwrap());
```
