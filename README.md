# sqlite-libicu-extension

Automated builds of the [SQLite ICU extension](https://www.sqlite.org/src/file/ext/icu/README.txt) as a loadable shared library for macOS and Linux.

Releases are created automatically whenever a new SQLite version is published, using GitHub Actions.

## Downloads

Pre-built binaries are available on the [Releases](../../releases) page.

## Usage

1. Download and unzip the archive for your platform.
2. Load the extension in SQL:

```sql
SELECT load_extension('/path/to/libicu');
```

Or from the SQLite CLI:

```sh
sqlite3 -cmd ".load /path/to/libicu"
```

Once loaded, the extension provides Unicode-aware functions such as `icu_load_collation()`, `lower()`, and `upper()` that correctly handle non-ASCII characters.

## License

The SQLite ICU extension source code is part of SQLite and is in the [public domain](https://www.sqlite.org/copyright.html).
