# RepCLI

A command-line tool for searching and replacing text patterns in files, built with Rust. RepCLI provides efficient text processing with support for case-sensitive and case-insensitive search operations.

## Features

- 🔍 Fast text search across file contents
- 🔄 Case-sensitive and case-insensitive search modes
- 📝 Line-by-line result display with matched content
- 🎯 Simple and intuitive command-line interface
- ⚡ Memory-efficient file processing

## Installation

### Prerequisites

- Rust 1.70 or higher
- Cargo (comes with Rust)

### Building from Source

```bash
# Clone the repository
git clone <your-repository-url>
cd RepCLI

# Build the project
cargo build --release

# The binary will be available at target/release/repcli
```

## Project Structure

```
RepCLI/
├── src/
│   ├── main.rs          # Entry point and CLI argument handling
│   └── lib.rs           # Core search functionality and logic
├── Cargo.toml           # Project metadata and dependencies
├── Cargo.lock           # Dependency lock file
├── .gitignore           # Git ignore rules
└── README.md            # This file
```

## Usage

### Basic Syntax

```bash
cargo run -- <query> <file_path>
```

Or if using the compiled binary:

```bash
./target/release/repcli <query> <file_path>
```

### Case-Insensitive Search

Set the `IGNORE_CASE` environment variable to enable case-insensitive searching:

```bash
IGNORE_CASE=1 cargo run -- <query> <file_path>
```

### Examples

**Case-sensitive search:**
```bash
cargo run -- "TODO" src/main.rs
```

**Case-insensitive search:**
```bash
IGNORE_CASE=1 cargo run -- "error" src/lib.rs
```

**Using the compiled binary:**
```bash
./target/release/repcli "function" README.md
```

## Configuration

### Environment Variables

- `IGNORE_CASE`: Set to any value (e.g., `1`, `true`) to enable case-insensitive search

## Development

### Running Tests

```bash
cargo test
```

### Running with Debug Output

```bash
cargo run -- <query> <file_path>
```

### Building for Production

```bash
cargo build --release
```

The optimized binary will be available at `target/release/repcli`.

## Error Handling

RepCLI provides clear error messages for common issues:

- **Insufficient arguments**: Reminds you to provide both query and file path
- **File not found**: Reports when the specified file doesn't exist
- **Read errors**: Displays file reading errors with context

## Performance

RepCLI is designed for efficiency:
- Streams file content line-by-line to minimize memory usage
- Uses Rust's zero-cost abstractions for optimal performance
- Compiled binary offers native speed

## Contributing

Contributions are welcome! Please feel free to submit issues or pull requests.

### Development Setup

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Make your changes
4. Run tests (`cargo test`)
5. Commit your changes (`git commit -m 'Add amazing feature'`)
6. Push to the branch (`git push origin feature/amazing-feature`)
7. Open a Pull Request

## License

[Specify your license here - e.g., MIT, Apache 2.0, GPL, etc.]

## Acknowledgments

Built with Rust 🦀 - A language empowering everyone to build reliable and efficient software.

---

**Note**: This tool is designed for educational purposes and demonstrates fundamental file I/O operations, environment variable handling, and command-line argument processing in Rust.