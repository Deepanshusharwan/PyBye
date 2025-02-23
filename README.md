# PyBye
PyBye: a Linux power management tool with a GTK-based GUI, enabling users to shutdown, reboot, suspend, lock, log out, or hibernate with ease. It supports custom commands, error handling, and dynamic theming, providing a user-friendly alternative to terminal-based system controls.

## Features
- Shutdown, reboot, suspend, lock, log out, or hibernate with a single click.
- Configurable commands, icons, and UI elements via a configuration file.
- Option to enable or disable confirmation prompts.
- Fully customizable GTK+3 styling using a CSS file.
- Support for fullscreen mode.
- Lightweight and fast execution.
- Simple and minimalistic user interface.

## Installation
### Dependencies
Ensure you have the following dependencies installed:
- Python 3
- GTK+3 and PyGObject (`gi.repository`)

To install dependencies on Debian-based systems:
```sh
sudo apt update
sudo apt install python3-gi gir1.2-gtk-3.0
```

For Arch-based systems:
```sh
sudo pacman -S python-gobject gtk3
```

For Fedora-based systems:
```sh
sudo dnf install python3-gobject gtk3
```

### Alternative dependency installation method
Alternatively you can also install the dependencies by the following method:
* cd into the PyBye directory
* make a venv and activate it (optional but recommended)
```shell
python -m venv .venv
source .venv/bin/activate
```
* if you made the virtual environment then check if its active , it should show the the path to the repo in you device if it worked
```shell
pip -V
```
* Now install all the dependencies through pip by the following method
```sh
pip install -r requirements.tx
```

### Clone the Repository
```sh
git clone https://github.com/yourusername/PyBye.git
cd PyBye
```

## Usage
Run the script using after installing all the dependencies:
```sh
python3 pybye.py
```

### Configuration
PyBye generates a configuration file at `~/.config/PyBye/pybye.conf` if it does not already exist. You can modify this file to customize commands, icons, and UI settings.

#### Example Configuration
```ini
[Commands]
button_one_command = shutdown now
button_two_command = reboot
button_three_command = systemctl suspend
button_four_command = dm-tool lock
button_five_command = gnome-session-quit --force
button_six_command = systemctl hibernate
```

#### UI Settings
```ini
[Size]
Width = 1920
Height = 1080
border_width = 480
icon_size = 6
dialog_height = 120
dialog_width = 150

[Options]
ask_for_confirmation = True
fullscreen_mode = True
```

### Keyboard Shortcuts
- Press `Escape` to exit the application.
- Use arrow keys to navigate between options.

## Customization
### Styling
You can customize the appearance of PyBye by modifying the `gtk_style.css` file. Below is an example of how to change the background color:

```css
@define-color bg-color rgba(40,40,40, 0.6);
@define-color text-color #ebdbb2;
```

### Changing Icons
Icons for buttons can be modified in the `pybye.conf` file under the `[Icons]` section. Example:
```ini
[Icons]
button_one_icon = system-shutdown-symbolic
button_two_icon = system-reboot-symbolic
```

## Troubleshooting
### Common Issues and Fixes
1. **Application does not start**
   - Ensure all dependencies are installed correctly.
   - Run the script in a terminal and check for error messages.

2. **Commands not working**
   - Check if the configured commands are correct.
   - Run the commands manually in a terminal to verify.

3. **Styling not applying**
   - Ensure that `gtk_style.css` exists and is properly formatted.
   - Restart the application after making changes.

## License
This project is licensed under the MIT License. You are free to modify and distribute it under the same license.

## Contributing
Pull requests and issue reports are welcome! Feel free to suggest enhancements, report bugs, or contribute code improvements.

### How to Contribute
1. Fork the repository.
2. Create a new branch.
3. Make your changes and commit them.
4. Submit a pull request.

## Future Plans
- Add support for additional desktop environments.
- Provide multi-language support.
