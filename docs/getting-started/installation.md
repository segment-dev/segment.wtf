---
sidebar_position: 1
---

# Installation

:::info
Currently only MacOS and Linux are supported
:::

## Download Binaries
To download the latest binaries for `segment-server` and `segment-cli` head over to the GitHub [releases](https://github.com/segment-dev/segment/releases) page.

## Build From Source
To build Segment from source you will need to install Rust, you can follow the instructions [here](https://www.rust-lang.org/tools/install) to setup Rust on your machine.

After you've installed Rust follow the instuctions below.

### Step 1
Clone the segment repository.
```bash
git clone git@github.com:segment-dev/segment.git
```

### Step 2
Build Segment using cargo.
```
cargo build --release
```

Final binaries can be found in `target/release` directory.
