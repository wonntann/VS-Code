# Troubleshooting
1. GitHub syncing is not working, enter the following command into the terminal:
``` bash
sudo apt install gnome-keyring
```
- Start the process over: click lower-left cog icon to open the menu with **Sync Settings**
- Select sign in option **GitHub**
- Default browser window will open to **Continue** confirmation
- When navigated to new webpage, click **Cancel** to not directly open up selected program. Copy the **Authorization Token**
- Navigate to VS Code, click on the bottom left text **Signing into GitHub...** and paste the URI into the prompt that popped up at the top of the VS Code window and hit **enter**
- Setting up will take a few moments 
