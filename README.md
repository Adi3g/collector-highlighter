# Collector Highlighter

Collector Highlighter is a Visual Studio Code extension that provides syntax highlighting for `.col` files used in the Collector library. This extension enhances the readability of `.col` files by highlighting keywords, comments, strings, and other syntax elements, making it easier to write and manage your Collector configurations.

## Features

- **Syntax Highlighting**: Highlights keywords, data types, strings, numbers, comments, and punctuation in `.col` files.
- **Supported Elements**:
  - Keywords: `VERSION`, `SOURCE`, `TRANSFORM`, `OUTPUT`, and more.
  - Data Types: Highlights field types like `int`, `float`, `string`, etc.
  - Comments: Line comments starting with `#`.
  - Strings: Double-quoted strings.
  - Numbers: Integer and float values.
  - Punctuation: Braces, colons, and equals signs.

## Installation

You can install Collector Highlighter directly from the Visual Studio Code Marketplace:

1. Open VS Code.
2. Go to the Extensions view by clicking on the Extensions icon in the Activity Bar on the side of the window or by pressing `Ctrl+Shift+X`.
3. Search for "Collector Highlighter".
4. Click **Install** to add the extension to your VS Code.

## Usage

Once installed, Collector Highlighter will automatically activate when you open a `.col` file in VS Code, providing syntax highlighting tailored for the Collector configuration files.

### Example

Here’s an example of a `.col` file with Collector Highlighter applied:

```plaintext
# Example .col file

VERSION 1.0

# Define Data Source
SOURCE sales_db TYPE sql {
    HOST "localhost"
    PORT 5432
    USERNAME "${DB_USERNAME}"
    PASSWORD "${DB_PASSWORD}"
    DATABASE "sales"
    QUERY "SELECT * FROM sales_data"
}

# Define Transformation
TRANSFORM unified_sales FROM sales_db {
    FIELD sale_date TYPE date FORMAT "%Y-%m-%d"
    FIELD amount TYPE float DEFAULT 0.0
}

# Define Output
OUTPUT unified_data TYPE parquet {
    PATH "/output/unified_sales.parquet"
    OPTIONS {
        COMPRESSION "gzip"
    }
}
