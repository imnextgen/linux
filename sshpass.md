# sshpass Command

`sshpass` is a simple utility for non-interactively performing password authentication with `ssh` and similar programs. It is useful for scripting automated SSH/SCP transfers when key-based authentication is not used.

## Installation on Ubuntu

You can install `sshpass` directly from the official Ubuntu repositories:

```bash
sudo apt update
sudo apt install sshpass
```

## Basic Usage

- **Simple SSH login with password:**
  ```bash
  sshpass -p 'your_password' ssh user@host
  ```

- **Copy a file to remote via SCP:**
  ```bash
  sshpass -p 'your_password' scp /local/file user@host:/remote/path
  ```

- **Read password from a file:**
  ```bash
  sshpass -f /path/to/password.txt ssh user@host
  ```

- **Prompt for password interactively:**
  ```bash
  sshpass -e ssh user@host
  # Password must be set in SSHPASS environment variable
  export SSHPASS='your_password'
  sshpass -e ssh user@host
  ```

## Common Options

- `-p password` : Provide password as argument (not recommended for security)
- `-f file` : Read password from file
- `-e` : Read password from environment variable `SSHPASS`
- `-d number` : Read password from file descriptor

## Security Note

Using `sshpass` with plain-text passwords can be insecure.  
Whenever possible, use SSH key-based authentication instead.

## More Information

- [sshpass man page](https://manpages.ubuntu.com/manpages/noble/en/man1/sshpass.1.html)
- `man sshpass`
