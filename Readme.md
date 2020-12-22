acc_reader, a seekable wrapper for input streams
================================================

[![Build Status][actions]](https://github.com/netvl/acc_reader/actions?query=workflow%3ACI)
[![crates.io][crates]](https://crates.io/crates/acc_reader)
[![docs][docs]](https://docs.rs/acc_reader)

  [actions]: https://img.shields.io/github/workflow/status/netvl/acc_reader/CI/master?style=flat-square
  [crates]: https://img.shields.io/crates/v/acc_reader.svg?style=flat-square
  [docs]: https://img.shields.io/badge/docs-latest%20release-6495ed.svg?style=flat-square

[Documentation](http://docs.rs/acc_reader)

acc_reader provides `AccReader`, a struct which wraps an arbitrary instance of `std::io::Read`
and provides an implementation of `std::io::Seek` for it. Naturally, this involves internal
buffering, therefore `AccReader` also provides `std::io::BufRead` interface, though its `read()`
method does not use this buffering. If/when specialization gets available in Rust, this could
change.

See [`AccReader`](http://docs.rs/acc_reader/struct.AccReader.html) documentation
for more information and examples.

## Usage

Just add a dependency in your `Cargo.toml`:

```toml
[dependencies]
acc_reader = "2.0"
```

## Changelog

### Version 2.0.0

Changed "beyond the end of stream" seek error kind to `UnexpectedEof`. This is a breaking
change.

### Version 1.0.0

Initial release

## License

This program is licensed under either of

 * Apache License, Version 2.0, ([LICENSE-APACHE](LICENSE-APACHE) or http://www.apache.org/licenses/LICENSE-2.0)
 * MIT license ([LICENSE-MIT](LICENSE-MIT) or http://opensource.org/licenses/MIT)

at your option.

### Contribution

Unless you explicitly state otherwise, any contribution intentionally submitted
for inclusion in the work by you, as defined in the Apache-2.0 license, shall be dual licensed 
as above, without any additional terms or conditions.
