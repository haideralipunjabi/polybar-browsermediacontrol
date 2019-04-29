# polybar-kdeconnect

A Browser Media Control module for [Polybar](https://github.com/jaagr/polybar)

![screenshot](screenshot.png)  
Demo with [Material Polybar](https://github.com/adi1090x/polybar-themes)

## Dependencies
* [python3](https://www.python.org)
* [pydbus](https://github.com/LEW21/pydbus)
* [Plasma Browser Integration](https://community.kde.org/Plasma/Browser_Integration)
* Iosevka Nerd Font

## Usage
Place the given script in some folder, and use it in your polybar `config` as
```  
[module/browsermediacontrol]  
type = custom/script  
exec = /path/to/files/browsermediacontrol
scroll-up = /path/to/files/browsermediacontrol --volume 1
scroll-down = /path/to/files/browsermediacontrol --volume -1 
interval = 0.1
````
*Note: You can change the integer argument in scroll-up/down to increase the speed of increase/decrease*
## Features:
* Customizable Title Truncate
* Volume Control on Scroll

## Customization
You can change the variables in [`browsermediacontrol`](browsermediacontrol) to customize the icons shown in [polybar](https://github.com/jaagr/polybar), text overflow length, etc.

