# Directory Creator and VS Code Opener Script

This Bash script allows you to create a new directory, navigate into it, and then open it in Visual Studio Code.

## Script

```bash
#!/bin/bash

# Ask for the name of the new directory
read -p "Enter the name of the new directory: " dir_name

# Create the directory and navigate into it
mkdir "$dir_name" && cd "$dir_name"

# Open Visual Studio Code in the current directory
code .
```

## Usage

1. Copy the script into a new file, for example, name it `create_and_open.sh`.
2. Give the script execute permissions:
   ```bash
   chmod +x create_and_open.sh
   ```
3. Run the script from your terminal:
   ```bash
   ./create_and_open.sh
   ```

> [!NOTE] This script assumes that `code` is set up as an alias in your `~/.zshrc` file to open Visual Studio Code. Ensure this alias exists before running the script.

## addint to ~/.zshrc

1. open termninal from home directory
```bash
nano ~/.zshrc
```
2. create an alias 
```bash
alias newcode='/Users/beto/create_and_open.sh'
```
3. source your new zshrc
```bash
source ~/.zshrc
```
4. let it rip
```bash
codenow
```


