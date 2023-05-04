      _                      _                    _                              
   __| |_   _____  _ __ __ _| | __      __ _ _ __(_)_   ____ _ _ __  _ __   __ _ 
  / _` \ \ / / _ \| '__/ _` | |/ /____ / _` | '__| \ \ / / _` | '_ \| '_ \ / _` |
 | (_| |\ V / (_) | | | (_| |   <_____| (_| | |  | |\ V / (_| | |_) | |_) | (_| |
  \__,_| \_/ \___/|_|  \__,_|_|\_\     \__,_|_|  |_| \_/ \__,_| .__/| .__/ \__,_|
                                                              |_|   |_|          



Adding new layout
	file location: /usr/share/X11/xkb/symbols/us
	add layout as in layout.txt at dvorak section of file

Adding new keyboard layout details - to update in gnome
	file location: /usr/share/X11/xkb/rules/evdev.xml
	add details as in layout-details.txt at us section of long xml file

---------------------

After this all works, file but pressing backspace(originally capslock) continuously won't invoke mutiple backspace, but only one.
To fix the issue, we need to run a command 'xmodmap -e "clear Lock"'

one way (the way I use)
	adding this command into .zshrc or .bashrc
	- now these are executed, when user opens terminal
	- user needs to open terminal at least once (after reboot) to fix this issue

another way
	adding cron job schedule at every reboot
	>crontab -e
	adding below line
	"@reboot sh path-to-capslock-repeatable-sh"
