# IntelliDock
Bash script for automatically turning on/off autohiding of the Dock if in "closed-display mode" on macOS.

## Short description
This script checks every 3 seconds if the device is in "clamshell mode" also known as "closed-display mode", if it is, it will disable Dock authohide and restart the Dock. If the device is not in closed-display mode, the script will enable Dock autohide.

The reason for this is because I have a 13 inch Macbook, so when I'm not docked, I don't want the dock to take up screen real estate, but when I'm at home (working on a larger screen) and the device is docked, I'd like to disable autohide. This just automates that process.

## Installation
1. Download or clone the script to your computer
2. Open a terminal window, navigate to the location where you saved the file (`cd /<folder>/`)
3. Run `chmod u+x Intellidock.sh` to allow the user to run the script
4. Run the script in the background `nohup ./Intellidock.sh > /dev/null 2>&1&`
5. Optionally set the script to run at startup (see [this link](https://stackoverflow.com/questions/6442364/running-script-upon-login-mac)).

## Extra
Something I've always hated about auto-hide on the dock is that there is a delay. 

### You can easily remove the autohide delay by entering this command in the terminal:
```
defaults write com.apple.dock autohide-delay -float 0 && defaults write com.apple.dock autohide-time-modifier -float 0.2 && killall Dock
```
### To reset to defaults, use the following command:
```
defaults delete com.apple.dock autohide-delay && defaults delete com.apple.dock autohide-time-modifier && killall Dock
```

## Author
Joni Van Roost, joni.VR@hotmail.com

## License
Intellidock is available under the MIT license. See the [LICENSE](https://github.com/JoniVR/IntelliDock/blob/master/LICENSE) file for more info.

## More
Feel free to submit a pull request, open an issue or fork this project. Any help is always appreciated.