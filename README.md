# sqlite-libicu-extension

Automated builds of the [SQLite ICU extension](https://www.sqlite.org/src/file/ext/icu/README.txt) as a loadable shared library for macOS ARM64, Linux AMD64, and Windows AMD64.

Releases are created automatically whenever a new SQLite version is published, using GitHub Actions.

## Downloads

Pre-built binaries are available on the [Releases](../../releases) page.

## Usage

1. Download and unzip the archive for your platform.
2. Load the extension from SQLite:

```sql
SELECT load_extension('/path/to/libicu');
```

Or from the SQLite CLI:

```sh
sqlite3
sqlite> .load /path/to/libicu
```

Once loaded, the extension provides Unicode-aware functions such as `icu_load_collation()`, `lower()`, and `upper()` that correctly handle non-ASCII characters.

## How Releases Work

A GitHub Actions workflow runs daily:

1. Fetches the current SQLite version from the SQLite fossil repository.
2. Skips if a release for that version already exists.
3. Builds `libicu.so` on `macos-14` (Apple Silicon), `ubuntu-latest` (AMD64), and `windows-latest` (AMD64) in parallel.
4. Creates a GitHub release tagged `v{version}` with all three zip archives attached.

## License

The SQLite ICU extension source code is part of SQLite and is in the [public domain](https://www.sqlite.org/copyright.html).
