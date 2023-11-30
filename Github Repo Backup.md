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

# Automation with Cron

To automate the backup process, you can set up a cron job that runs the script at regular intervals. Here's how to do it:

1. **Open the Crontab Configuration**:
   
In your terminal, run `crontab -e` to edit the cron jobs for your user.

2. **Add a Cron Job**:

In the crontab editor, add a line that specifies when and how often the script should run. For example:
     
     ```
     0 2 * * * /path/to/backup_github_repos.sh
     ```
     This example sets the script to run at 2 AM every day. Adjust the schedule to your preference.
     - The format is `minute hour day month day-of-week command`.
     - Ensure you provide the full path to `backup_github_repos.sh`.

3. **Save and Exit**:

Save the file and exit the editor. Cron will automatically install the new cron job.

### Understanding Cron Syntax:

- `* * * * *` consists of five fields: minute (0-59), hour (0-23), day of the month (1-31), month (1-12), and day of the week (0-7, where 0 and 7 are Sunday).
- Use commas to specify a list (e.g., `5,10` in the hour field means 5 AM and 10 AM).
- Use hyphens to specify ranges (e.g., `1-5` in the day-of-week field means Monday to Friday).
- Use the asterisk `*` to specify 'any'.

### Notes on Automation:

- Ensure your computer is running at the scheduled time for the backup.
- The script will run in the background without interrupting your activities.
- Review the backup periodically to ensure it's running as expected.

# Combining Wake Scheduling in MacOS + Cron 

To automate the backup process and ensure it runs even when your Mac is asleep, you can set up a cron job and schedule wake-up times using the Terminal.

### Setting Up a Wake Schedule with Terminal

You can use the `pmset` command to schedule your Mac to wake or power on at specific times:

1. **Open Terminal**:

Find Terminal in the Applications > Utilities folder, or use Spotlight to search for it.

2. **Schedule a Wake or Power On Event**:

Use the `pmset` command to set a wake schedule. For example, to wake your Mac every weekday at 7:30 AM:
     ```
     sudo pmset repeat wakeorpoweron MTWRFSU 07:30:00
     ```
   Replace `MTWRFSU` and `07:30:00` with the days and time you prefer.

3. **Verify Your Schedule**:
   
To check your current wake schedule, run:
     ```
     pmset -g sched
     ```

4. **Cancel a Scheduled Event**:
   
To remove a scheduled wake event, use:
     ```
     sudo pmset repeat cancel
     ```

### Setting Up Your Cron Job

1. **Edit Crontab**:
   
Run `crontab -e` in the Terminal to edit your cron jobs.

2. **Add Your Backup Script to Cron**:
   
Add a line for your backup script, timed a few minutes after the wake schedule:
     ```
     0 2 * * * /path/to/backup_github_repos.sh
     ```
   This example sets the script to run at 2 AM daily. Adjust as needed.

3. **Save and Close**:
   
Save the changes and exit the editor.

### Notes

- Ensure your Mac is connected to power, as some models might not wake when on battery power.
- Align the cron job timing closely with the wake schedule.
- Check security settings if your Mac requires a password immediately after sleep, as this might prevent scheduled tasks from running.




