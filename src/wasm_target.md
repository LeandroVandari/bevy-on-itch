# Adding the `wasm32-unknown-unknown` target
In order to compile your game to WASM, you need to add the `wasm32-unknown-unknown` target to `rustup`. That can be done with the following command:
```
rustup target add wasm32-unknown-unknown
```
After doing this, you'll be able to compile your game to WASM by running
```
cargo build --target wasm32-unknown-unknown
```

<div class="warning">
If you get an error running cargo build similar to this:

```
error: The wasm32-unknown-unknown targets are not supported by default; 
you may need to enable the "wasm_js" configuration flag.
Note that enabling the `wasm_js` feature flag alone is insufficient.
For more information see: https://docs.rs/getrandom/0.3.3/#webassembly-support
```
Do not despair. This will be fixed in the [Using random numbers](./random_numbers.md) chapter.
</div>