# Window Settings
When creating your window, it's important to set some options in your `primary_window`:
* `fit_canvas_to_parent: true` -- makes it so the window scales to fill the whole canvas it ocupies, not leaving any borders. However, only this is not enough.
* `canvas: Some("#bevy")` -- makes it so you can create your own canvas that fills the whole provided area. Otherwise, the WASM will create its own canvas that doesn't fill it.
* `prevent_default_event_handling: false` -- this is more optional. It allows you to press `esc` to exit the fullscreen, for example. If you handle all events properly in your game, you don't need to turn it off.