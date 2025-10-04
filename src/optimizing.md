# Further optimizing
Although the compiler can optimize a lot of the WASM for us, `wasm-opt` can often take it a step further.
<div class="warning">
This should be run AFTER `wasm-bindgen`. Otherwise, you will get errors.
</div>

## Installing
```
cargo install wasm-opt --locked
```

## Running
```
wasm-opt -Os --output wasm_output/game_bg.wasm wasm_output/game_bg.wasm
```
> Note: Replace `game` with whatever `--out-name` you passed to `wasm-bindgen`.

* `-Os` means we're optimizing for size

