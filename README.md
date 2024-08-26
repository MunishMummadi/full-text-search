# Full Text Search

A simple full-text search engine for Wikipedia abstract dumps written in Go. This project demonstrates how to load, index, and search through Wikipedia abstract data using a custom-built indexing and search mechanism.

## Features

- **Load Wikipedia Abstract Dumps:** Efficiently loads and parses Wikipedia abstract dump files in XML format.
- **Indexing:** Creates an index of documents for fast search operations.
- **Full-Text Search:** Supports searching for specific queries across all indexed documents.
- **Performance Logging:** Logs the time taken for loading, indexing, and searching operations.

## Installation

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/MunishMummadi/full-text-search.git
   cd full-text-search
   ```

2. **Install Dependencies:**

   Make sure you have Go installed (version 1.16 or higher recommended). Then, run:

   ```bash
   go mod tidy
   ```

## Usage

### Command-Line Interface

You can run the program using the `go run` command. The program accepts two flags:

- `-p`: Path to the Wikipedia abstract dump (default: `enwiki-latest-abstract1.xml.gz`).
- `-q`: Search query (default: `Small wild cat`).

### Example Usage

```bash
go run main.go -p /path/to/enwiki-latest-abstract1.xml.gz -q "Your search query"
```

### Example

```bash
go run main.go -p enwiki-latest-abstract1.xml.gz -q "Small wild cat"
```

This command will load the Wikipedia abstract dump from the specified path, index the documents, and search for the query "Small wild cat". The results will be logged to the console.

## Project Structure

```plaintext
full-text-search/
├── main.go            # Entry point of the program
├── go.mod             # Go module file
├── go.sum             # Go dependencies file
└── utils/
    ├── document.go    # Document struct and LoadDocuments function
    ├── filter.go      # Filtering functionality for documents
    ├── index.go       # Indexing functionality for documents
    ├── tokenizer.go   # Tokenizer for processing text
    ├── filter_test.go # Tests for filter.go
    ├── index_test.go  # Tests for index.go
    └── tokenizer_test.go # Tests for tokenizer.go
```

## Contributing

Contributions are welcome! If you'd like to contribute, please fork the repository and use a feature branch. Pull requests are warmly welcome.

1. Fork the repository
2. Create a new feature branch (`git checkout -b feature-branch`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin feature-branch`)
5. Create a new Pull Request

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

## Acknowledgments

- The project uses the [Snowball](https://github.com/kljensen/snowball) stemming algorithm.
- [Testify](https://github.com/stretchr/testify) is used for unit testing.
- Inspired by Wikipedia and its open data.
