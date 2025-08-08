# rsync Command

`rsync` is a fast and versatile file copying tool used to synchronize files and directories between two locations over local or remote systems.

## Installation on Ubuntu

`rsync` is available in the Ubuntu repositories and can be installed with:

```bash
sudo apt update
sudo apt install rsync
```

## Basic Usage

- **Copy files locally:**
  ```bash
  rsync -avh source/ destination/
  ```
- **Copy files to a remote server:**
  ```bash
  rsync -avh /local/dir/ user@remote:/remote/dir/
  ```
- **Copy files from a remote server:**
  ```bash
  rsync -avh user@remote:/remote/dir/ /local/dir/
  ```

## Common Options

- `-a` : Archive mode (preserves permissions, times, symbolic links, etc.)
- `-v` : Verbose output
- `-h` : Human-readable numbers
- `--delete` : Delete files in the destination that don't exist in the source
- `-z` : Compress file data during transfer

## Example: Mirror a Directory

```bash
rsync -avh --delete /source/dir/ /backup/dir/
```

## More Information

- [rsync man page](https://manpages.ubuntu.com/manpages/jammy/en/man1/rsync.1.html)
- `man rsync`
