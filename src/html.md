# Creating an html file
Although `wasm-bindgen` made the WASM accessible through the javascript, we still need to initiate it (and create our canvas to put the game in). Itch will load an `index.html` file you pass to it, which we can leave with the following contents:
```html
<!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8" />
        <script type="module">
            import init from "./game.js";
            init();
        </script>
    </head>
    <body>
        <canvas id="bevy"></canvas>
    </body>
</html>
```

Make sure to put the file in the same folder as the outputs from `wasm-bindgen`.