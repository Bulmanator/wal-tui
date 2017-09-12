# wal-tui
A colour scheme generator for T-UI Console Launcher  
The launcher itself can be found at these various locations:  
- GitHub: https://github.com/Andre1299/TUI-ConsoleLauncher  
- Google Play: https://play.google.com/store/apps/details?id=ohi.andre.consolelauncher  
- F-Droid: https://f-droid.org/packages/ohi.andre.consolelauncher  

# Credit
All credit for the colour generation from image goes to **pywal** and its creator **dylanaraps**  
This can be found here: https://github.com/dylanaraps/pywal

## Dependencies
- Any computer which can use `python` and `imagemagick`
- `python 3.5+`
- `imagemagick` for colour scheme generation

### Usage
To use wal-tui all you need to do is pass the script a valid image, however it can be customised more if you like:  
```
Usage: tui-wal [-h] [-c] [-s] [-t] [-a] [-g] [-l]
	        [-n][-f "format"] "/path/to/image"

tui-wal generate colour schemes for T-UI Launcher

Optional Arguments:
  -h: Show this message
  -c: Don't generate colours.xml

Suggestions Configuration:
  -s: Don't show suggestions
  -t: Enable transparent suggestions
  -a: Don't suggest aliases
  -g: Don't suggest app groups
  -l: Disable click to launch suggestions

Notifications Configuration:
  -n: Don't show notifications
  -f "format": The format of notifications (Default: "[%app] %ttl - %txt")
	             Formatting options:
	             - %app: Application name
	             - %pkg: Package name
	             - %ttl: Notification title
	             - %txt: Notification text
 ```  
Running the script will output a theme.xml, suggestions.xml and a notifications.xml file which can then be copied to the t-ui folder on your device. Optionally, a colours.xml can be generated to reference the colours generated.  
  
**Disclaimer: This will overwrite your notification preferences and set them back to default, I plan on working on this issue. I recommend backing up at least your notifications.xml, if not all of your configuration xml files, before using this script.**
 
### Termux
The script can be run via termux on some devices. You can install the required packages with `pkg install python` and `pkg install imagemagick`. You will need to edit the shebang from `#!/usr/bin/env python3` to `#!/data/data/com.termux/files/usr/bin/env python3` and then you can then copy the scrpit to /data/data/com.termux/files/usr/bin so it can be run from anywhere. I plan on creating a termux specific version which will automatically overwrite the files in your t-ui folders so all you need to do is run the script and restart T-UI.  
  
The convert command from imagemagick can throw up a 'Segmentation Fault' while choosing the colours meaning it will not work on all devices. See here for more details: [Imagemagick convert segfaults #1314](https://github.com/termux/termux-packages/issues/1314).
