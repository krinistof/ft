# ft - first timestamp, fits target

Have you ever tried to handle many photos, songs from various pendrives, sources where you had many copies of almost the same file? This project tries to help you handle that.

`ft` is a command-line tool for organizing media files from a source ("funnel") directory into a structured `year/month/day` hierarchy in an output directory. For each media, it collects all the different timestamps found, and stores it at the first timestamp's directory.

This is the base structure. After various custom analytics, indices can be integrated (eg. from other tools) for the most efficient data aggregation.

## Basic Usage

For integrating an old archive to the collection use:
```bash
ft plan --funnel old/media --output sorted
ft apply
```

**Subcommands:**


`ft plan`
Analyzes the funnel's files and creates an execution plan.
* `-f, --funnel <PATH>`: Source directory of media files.
* `-o, --output <PATH>`: Target directory for organized media.
* `--move`: Move files instead of copying them.

`ft show`
Show what would be done based on the plan

`ft apply`
* Execute plan

## Installation

### Build from source
Install Rust from [rustup.rs](https://rustup.rs).

To build the latest binary run:
```bash
cargo install --git https://github.com/krinistof/ft
```

## Features

* Detects dates from EXIF, filenames (e.g., `IMG_YYYYMMDD_...`, `YYYY-MM-DD_...`), and file metadata.
* Creates `YYYY/MM/DD` directory structure.
* Handles filename collisions by appending a counter.
