# TexTalk

A simple progressive web application (PWA), which enable users to capture an image, get the text contents read aloud.


## Depedencies

### Object Character Recognition (OCR) using Web Assemply (WASM)

The app contains a WASM module, which is based on the [ocrs crate](https://crates.io/crates/ocrs), of the [ocrs project](https://github.com/robertknight/ocrs). A nicely crafted Rust crate, which bases its OCR engine on recognition and detection models in [RTen](https://github.com/robertknight/rten) format.


### Finetuned models

The [ocrs Hugging Face Model](https://huggingface.co/robertknight/ocrs) contains pre-trained models for the English language. Since the auther of TexTalk is Danish, finetuned models are used in this project, which support the Danish language, as well as the English language.

The finetuned models are [available on Hugging Face](https://huggingface.co/dennis-isaksen/ocrs-finetuned-additional-lang).

The finetuning is done using [PyTorch](https://github.com/pytorch/pytorch), and following the [Training guide](https://github.com/robertknight/ocrs-models/blob/main/docs/training.md) provided in the [ocrs-models project](https://github.com/robertknight/ocrs-models).


# Building the Project

Besides having [Rust and Cargo installed](https://www.rust-lang.org/tools/install), one needs to have wasm-pack installed, to build the WASM module:
```bash
cargo install wasm-pack
```

Afterwards, the WASM module can be build using this command.
```bash
wasm-pack build --target web
```