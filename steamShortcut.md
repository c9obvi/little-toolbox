# Launch Liftoff from Steam Script

This guide provides instructions for setting up a bash script to automate the launching of the game "Liftoff" through Steam.

## Prerequisites

- Ensure you have Steam installed on your system.
- You should know the Steam ID of the game you want to launch. For Liftoff, it is `410340`.

## Script

The script performs the following actions:

1. Opens Steam.
2. Waits for a predefined amount of time (10 seconds by default) to allow Steam to start up.
3. Launches Liftoff via Steam using its Steam ID.

### Script Content

Copy the following script into a new file:

```
#!/bin/bash

# Open Steam
open -a steam

# Wait for Steam to launch (adjust time if necessary)
sleep 10

# Launch Liftoff via Steam with its Steam ID
open steam://run/410340
```

# Open Steam
open -a steam

# Wait for Steam to launch (adjust time if necessary)
sleep 10

# Launch Liftoff via Steam with its Steam ID
open steam://run/410340

### Setup Instructions

1. **Create the Script File**: Create a new file with a `.sh` extension, for example, `launch_liftoff.sh`.
2. **Make the Script Executable**: Run the command `chmod +x launch_liftoff.sh` in your terminal to make the script executable.
3. **Execute the Script**: Run the script by typing `./launch_liftoff.sh` in your terminal.

## Customization

- You can modify the `sleep 10` line in the script to adjust the waiting time according to how quickly Steam starts up on your system.
- Replace `410340` with the Steam ID of any other game you wish to launch in a similar manner.

## Troubleshooting

If the game does not launch, ensure that:

- Steam is properly installed on your system.
- The Steam ID is correct.
- Steam is able to launch the game manually.

For further issues, consult the game's support forums or Steam support.

## License

[my license] lol

---
Generated for use on GitHub - [0xBerto](https://twitter.com/0xberto)
