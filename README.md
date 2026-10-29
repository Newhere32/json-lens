# JSON Lens

A small, dependency-free command-line tool to validate and consistently format JSON files.

## Features

- Validates input and reports readable parse errors.
- Pretty-prints JSON using a configurable indentation width.
- Optionally sorts object keys for stable diffs.
- Reads from a file or standard input and writes to a file or standard output.
- Supports a check-only mode that validates without changing or printing the document.
- Uses only the Python standard library.

## Requirements

Python 3.10 or newer.

## Quick start

```bash
python -m json_lens data.json
python -m json_lens data.json --indent 4 --sort-keys
python -m json_lens data.json --check
python -m json_lens data.json --output formatted.json
cat data.json | python -m json_lens -
```

On Windows PowerShell, use `Get-Content -Raw data.json | python -m json_lens -` to pipe a file.

`--check` exits with code `0` for valid JSON and `1` for invalid JSON. Formatting errors are written to standard error.

## Development and tests

From the repository root:

```bash
python -m unittest discover -s tests -v
```

No third-party packages are required.

## Limitations

This tool formats JSON; it does not validate application-specific schemas. It intentionally rejects non-standard constants such as `NaN` and `Infinity`.

## Licence

Released under the [MIT License](LICENSE).
