# Running locally
If you want to test behavior for your web build, it's important that you can run it locally. For that, you need to add a `runner` to execute your WASM code.

First of all, we need to install that runner, by doing
```
cargo install wasm-server-runner
```
Then, to set it to be the default runner when compiling to wasm, add the following to `.cargo/config.toml`:
```toml
[target.wasm32-unknown-unknown]
runner = "wasm-server-runner"
```

After that, you can locally run your game by doing
```
cargo run --target wasm32-unknown-unknown
```