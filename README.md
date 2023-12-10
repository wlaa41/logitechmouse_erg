Mouse Button Bindings with xbindkeys and xautomation
# Mouse Button Bindings with xbindkeys and xautomation
This guide provides instructions on how to bind mouse buttons to keyboard actions in Ubuntu using
`xbindkeys` and `xautomation`.
## Prerequisites
- Ubuntu (or a similar Linux distribution)
- Mouse with additional buttons you wish to bind
## Installation
### xbindkeys
`xbindkeys` is a program that allows you to launch shell commands with your mouse or keyboard
under X Window.
Install xbindkeys:
```
sudo apt update
sudo apt install xbindkeys
```
### xautomation
`xautomation` is a suite of tools which includes `xte` for simulating keyboard input.
Install xautomation:
```
sudo apt install xautomation
```
## Configuration
### Step 1: Create Default Config
Generate the default `.xbindkeysrc` file in your home directory.
### Step 2: Edit Config File
Edit the `.xbindkeysrc` file to include the custom mouse button bindings. The following example
configuration maps various mouse buttons to keyboard actions:
```
# Map button 6 to "Enter"
"xte 'key Return'"
 b:6
# Map button 7 to "Backspace"
"xte 'key BackSpace'"
 b:7
# Map button 8 to "Paste"
"xte 'keydown Control_L' 'key v' 'keyup Control_L'"
 b:8
# Map button 9 to "Copy"
"xte 'keydown Control_L' 'key c' 'keyup Control_L'"
 b:9
```
This configuration is saved in a file named `keybindx` in the repository. You can use this as a
reference or customize it according to your needs.
## Usage
After editing and saving the `keybindx` file, restart `xbindkeys` to apply the changes:
```
killall xbindkeys
xbindkeys
```
Test the configuration to ensure the mouse buttons perform the intended actions.
