# llama-cpp-rs-cluster: prism-0.1.159 branch

Rust bindings for llama.cpp, carried as the crates.io-published sources of
`llama-cpp-2` and `llama-cpp-sys-2` at version 0.1.159, with the following
changes:

- `llama-cpp-sys-2/llama.cpp` is a git submodule pinned to
  Guerra10/prism-llama-cpp @ 73bfe6cc485554822f80c473a3c0c4f25e80f41b
  (replacing the crate's bundled source tree).
- `llama-cpp-sys-2/build.rs` additionally emits `cargo:src_dir=<path>` so
  direct dependents can locate the llama.cpp sources via `DEP_LLAMA_SRC_DIR`.
- `llama-cpp-2` carries two source-level compatibility patches for this
  llama.cpp tree: a pinned `VocabType::TEST` discriminant and a legacy
  `LlamaModel` tokenizer surface recreated over the `vocab()` API.

Upstream project: https://github.com/utilityai/llama-cpp-rs
(MIT OR Apache-2.0). This branch is consumed as a `[patch.crates-io]` git
source; it is not published to crates.io.
