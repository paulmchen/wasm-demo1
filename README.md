# DEMO: Compile a RUST code into WASM binary and then run it under the  wasmer runtime
## Example: a RUST lib used to sum two integer numbers

### Pre-requisite: Install wasmer runtime
`curl https://get.wasmer.io -sSfL | sh`

### Build wasmer from the source:
See: https://docs.wasmer.io/ecosystem/wasmer/building-from-source

### Install WASM toolchain
`rustup target add wasm32-unknown-unknown`

### Install WASM-gc
`cargo install wasm-gc`

### Setup RUST env:
Setup RUST env.  https://docs.wasmer.io/integrations/rust/setup

### Compile RUST into WASM
`cargo build --target wasm32-unknown-unknown --release`

### Shrink the Wasm Output
`wasm-gc target/wasm32-unknown-unknown/release/sum.wasm`

### Run .wasm binary
`cd target/wasm32-unknown-unknown/release/`

`wasmer sum.wasm -i sum 128  22`
