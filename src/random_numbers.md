# Using random numbers
Until now, if you've tried to build your developed game, you might have seen errors about the `wasm32-unknown-unknown` targets not being supported by default. The reason for that are random numbers.

When using the `rand` crate, by default, you won't be able to compile your crate for the web. In order to do that, you'll need to:

## Enable `getrandom`'s `wasm_js` feature
`getrandom` is a dependency of `rand`. They are the one who control the "backend" of things. In order to be able to use `getrandom` on WASM, you'll need to enable their `wasm_js` feature. This can be done by adding, under your `[dependencies]` in `Cargo.toml`:
```toml
getrandom = { version = "0.3.3", features = ["wasm_js"] }
```

## Compile with proper flags
Besides enabling the `wasm_js` feature, the project must be compiled with a compiler flag enabled. This can be done by either
### Building your project with the flags
I.e by doing 
```
RUSTFLAGS='--cfg getrandom_backend="wasm_js"' cargo build
```
### Setting, in your `.cargo/config.toml`:
```toml
[build]
rustflags = ["--cfg", 'getrandom_backend="wasm_js"']
```