# Iterating faster: a Makefile
In order to make the whole process faster, you can have a `Makefile` that runs all needed steps in order:
```
build:
    RUSTFLAGS='--cfg getrandom_backend="wasm_js"' cargo build --profile wasm-release --target wasm32-unknown-unknown
    mkdir -p wasm_output
    wasm-bindgen --out-name game --target web target/wasm32-unknown-unknown/wasm-release/PROJECT_NAME.wasm --out-dir wasm_output
    wasm-opt -Os --output wasm_output/game_bg.wasm wasm_output/game_bg.wasm
    cp -r assets/ wasm_output/assets/
    echo '''<!DOCTYPE html> \
        <html lang="en"> \
        <head> \
            <meta charset="UTF-8" /> \
            <script type="module"> \
                import init from "./game.js"; \
                init(); \
            </script> \
        </head> \
        <body> \
            <canvas id="bevy"></canvas> \
        </body> \
    </html>''' > wasm_output/index.html
```
(simply make sure to replace PROJECT_NAME with your actual project's name)

Now, in order to build your game, run `make`, and zip the contents of the `wasm_output` folder.