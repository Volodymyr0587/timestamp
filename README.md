# DateTime Filename Generator

A simple Bash script that generates a timestamp in a customizable format. It is useful for creating unique filenames, naming backup archives, organizing files, and adding timestamps to logs.

## Features

- Generates the current date and time in `YYYY_MM_DD_HHMMSS` format by default.
- Supports a custom separator between date components.
- Uses the system date and time.
- Requires no additional dependencies.

## Requirements

- Bash
- GNU `date` or a compatible implementation

## Installation

1. Save the script as `timestamp`.
2. Make it executable:

    ```bash
    chmod +x timestamp
    ```

3. Run it directly:

    ```bash
    ./timestamp
    ```

To make it available system-wide, copy it to `/usr/local/bin/`:

```bash
sudo install -m 755 timestamp /usr/local/bin/timestamp
```

## Usage

```bash
timestamp [SEPARATOR]
```

The `SEPARATOR` argument is optional. If omitted, the script uses an underscore (`_`).

### Examples

**Default separator:**

```bash
timestamp
```

Example output:

```text
2026_10_14_174230
```

**Hyphen separator:**

```bash
timestamp -
```

Example output:

```text
2026-10-14-174230
```

**Dot separator:**

```bash
timestamp .
```

Example output:

```text
2026.10.14.174230
```

**No separator:**

```bash
timestamp ""
```

Example output:

```text
20261014174230
```

## Output Format

| Component | Description            | Example  |
| --------- | ---------------------- | -------- |
| `YYYY`    | Four-digit year        | `2026`   |
| `MM`      | Two-digit month        | `10`     |
| `DD`      | Two-digit day          | `14`     |
| `HHMMSS`  | Time in 24-hour format | `174230` |

The separator is applied between the year, month, day, and time components. The time itself always uses the `HHMMSS` format without separators.

## Use Cases

Generate timestamped filenames:

```bash
backup_file="backup_$(timestamp).tar.gz"
```

Create a timestamped directory:

```bash
mkdir "$(timestamp)"
```

Add a timestamp to a log entry:

```bash
echo "[$(timestamp)] Backup completed" >> backup.log
```

## License

Use, modify, and distribute this script freely. Add a license file if you intend to publish the project with a specific open-source license.
