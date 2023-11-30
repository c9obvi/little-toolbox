# GitHub Repository Backup Script

This script is designed to backup all your GitHub repositories (both public and private) to your local machine. It uses the GitHub API to fetch your repositories and then clones or updates them in a local directory.

## Getting Started

### Prerequisites

- Bash shell (usually available on macOS and Linux systems)
- `git` installed on your system
- A GitHub Personal Access Token (PAT) with `repo` scope for accessing private repositories

### Setup

1. **Generate a Personal Access Token (PAT) on GitHub**:
   - Go to [GitHub's Token Settings](https://github.com/settings/tokens).
   - Click on "Generate new token".
   - Give your token a descriptive name, select the `repo` scope, and click "Generate token".
   - **Important**: Copy the token and keep it secure.

2. **Create the Backup Script**:
   - Create a new file named `backup_github_repos.sh`.
   - Paste the following script into the file:

    ```bash
    #!/bin/bash

    # Set your GitHub username and PAT
    GITHUB_USERNAME="your_username"
    GITHUB_TOKEN="your_token"

    # Directory to store the backup
    BACKUP_DIR="github_backup"
    mkdir -p "$BACKUP_DIR"

    # Fetch the list of repositories and clone or update them
    curl -s -H "Authorization: token $GITHUB_TOKEN" "https://api.github.com/users/$GITHUB_USERNAME/repos?per_page=100" | grep -o 'git@[^"]*' | while read -r repo
    do
      repo_name=$(basename "$repo")
      target_dir="$BACKUP_DIR/$repo_name"

      if [ -d "$target_dir" ]; then
        echo "Updating $repo"
        git -C "$target_dir" pull
      else
        echo "Cloning $repo"
        git clone "$repo" "$target_dir"
      fi
    done
    ```

    - Replace `your_username` and `your_token` with your GitHub username and the generated PAT.

3. **Make the Script Executable**:
   - Run the following command in the terminal: `chmod +x backup_github_repos.sh`

### Usage

- Run the script by executing `./backup_github_repos.sh` in your terminal.
- The script will clone or update all your GitHub repositories in a folder named `github_backup` in the current directory.

## Notes

- Handle your Personal Access Token with care. It's recommended not to hardcode it in the script if you're sharing it.
- The script currently fetches up to 100 repositories. If you have more, adjust the pagination in the API request.
- The script does not delete local repositories that no longer exist on GitHub.