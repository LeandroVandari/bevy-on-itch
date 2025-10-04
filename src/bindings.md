# Generating bindings
Regular WASM files can't simply be run by the browser. They need to be properly packaged and called by JavaScript code. In order to build that interface, we use `wasm-bindgen`:

## Installing
```
cargo install wasm-bindgen-cli
```
## Running
```
wasm-bindgen --out-name game \
    --out-dir wasm_output \
    --target web \
    target/wasm32-unknown-unknown/wasm-release/PACKAGE_NAME.wasm 
```
(remember to replace `PACKAGE_NAME` with your actual package's name, as in the `Cargo.toml`)

* `--out-name` specifies the name that the output files should have.
* `--target web` tells it we want to compile to run on the web, in a browser.
* `--out-dir` specifies where to put the generated files. If the `wasm_output` dir doesn't exist, this will error.

