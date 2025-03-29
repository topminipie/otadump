<!-- markdownlint-configure-file {
  "MD033": false,
  "MD041": false
} -->

<div align="center">

# otadump

**`otadump` helps you extract partitions from Android OTA files.** <br />
Partitions can be individually flashed to your device using `fastboot`.

Compared to other tools, `otadump` is significantly faster and handles file
verification - no fear of a bad OTA file bricking your device.

![Demo][demo]

</div>

## Features

|                              | [topminipie/otadump] | [ssut/payload-dumper-go] | [vm03/payload_dumper]                     |
| ---------------------------- | --------------------- | ------------------------ | ----------------------------------------- |
| Input file verification      | ✔                     | ✔                        |                                           |
| Output file verification     | ✔                     |                          |                                           |
| Extract selective partitions | ✔                     | ✔                        | ✔                                         |
| Parallelized extraction      | ✔                     | ✔                        |                                           |
| Runs directly on .zip files  | ✔                     | ✔                        |                                           |
| Incremental OTA support      |                       |                          | [Partial][payload_dumper-incremental-ota] |

## Benchmarks

Comparing the time taken to extract all partitions from a few sample files
(lower is better):

![Benchmarks][benchmarks]

**Note:** `otadump` was run with args `--no-verify -c 12` and `payload-dumper-go` was run with args `-c 12`

System specifications:

- Processor: AMD Ryzen 5 5600X (12) @ 3.700GHz
- RAM: 16 GiB
- OS: Pop!_OS 22.04 / Linux 6.0.6
- SSD: Samsung 970 EVO 250GB

## Installation

Download a pre-built binary: [Releases](https://github.com/topminipie/otadump/releases)

## Usage

Run the following command in your terminal:

```sh
# Run directly on .zip file.
otadump ota.zip

# Run on payload.bin file.
otadump payload.bin
```

## Contributors

- [Kartik Sharma][crazystylus]
- [Ajeet D'Souza][ajeetdsouza]

[ajeetdsouza]: https://github.com/ajeetdsouza
[benchmarks]: contrib/benchmarks.svg
[crazystylus]: https://github.com/crazystylus
[topminipie/otadump]: https://github.com/topminipie/otadump
[demo]: contrib/demo.gif
[payload_dumper-incremental-ota]: https://github.com/vm03/payload_dumper/issues/53
[ssut/payload-dumper-go]: https://github.com/ssut/payload-dumper-go
[vm03/payload_dumper]: https://github.com/vm03/payload_dumper
