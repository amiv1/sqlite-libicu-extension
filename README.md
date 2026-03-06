# sqlite-libicu-extension

Automated builds of the [SQLite ICU extension](https://www.sqlite.org/src/file/ext/icu/README.txt) as a loadable shared library for macOS and Linux.

Releases are created automatically whenever a new SQLite version is published, using GitHub Actions.

## Use case

Primary purpose of this is to be able to load ICU extension into Beets: https://beets.io/

See this issue for details: https://github.com/beetbox/beets/issues/6382#issuecomment-4013188931

It may be possible to use it outside of Beets, but for that you're on your own.

## Downloads

Pre-built binaries are available on the [Releases](../../releases) page.

## Usage with Beets

Extract archive and place it in `~/.config/beets/lib/`

Then configure your beets `beet config -e`:

```yaml
plugins:
  - loadext

loadext:
  - lib/libicu.so
```

## License

The SQLite ICU extension source code is part of SQLite and is in the [public domain](https://www.sqlite.org/copyright.html).
