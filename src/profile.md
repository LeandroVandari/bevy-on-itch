# Setting a wasm profile
When compiling for WASM, the requirements are often different than on a regular build. For example, it's much more important that a binary be smaller, so that it can be quickly downloaded and loaded, and the user experiences less latency. For that reason, I'd recommend making a `wasm-release` profile, that better encapsulates those requirements. In your `Cargo.toml`, add:

```toml
[profile.wasm-release]
inherits="release"
opt-level="z"
strip="debuginfo"
lto=true
codegen-units=1
```
This will make for the most-optimized smallest binary you can have, allowing for a better experience for your players.

To compile, now, use:
```
cargo build --profile wasm-release --target wasm32-unknown-unknown
```