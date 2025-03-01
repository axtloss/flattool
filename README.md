# flattool
![Flattool Logo, a simple icon of a tower crane holding a dangling letter F in front of "lattool"](flattool_logo-name.png)
Flattool is a command line script that should make dealing with flatpaks through the command line better.

## Flattool has 3 main uses:
1. Flattool can handle multiple installs in a loop instead of all at once, meaning that if a match is not found, your entire queue is not lost.
2. Flattool makes running apps from the command line easier. Instead of needing to use the app's full Application ID, you need only to type in a query for flattool to match.
3. Flattool can help clean up orphaned user files. Flattool will find any user data files that do not have an associated flatpak installed, and either trash the folder or attempt to install the flatpak, based on your choice.

## Important things to note:
- This is my first big project, there's a reason the version number doesn't start with a 1. All this to say that there could be unkown problems with this code currently.
- Flattool assumes that flatpak user data is stored within ~/.var/app (the default location for these folders).
- Flattool is not a replacement for flatpak, it merely sends the appropriate flatpak commands for the desired action.
- Flattool uses `gio trash` to delete folders, not `rm`, so if you want to clear your diskspace you'll still need to empty your trash. This is to avoid any perminant deletion of files.

## Dependancies
- gio. As said before, this script uses `gio trash`, so gio must be installed. gio is part of glib2, so make sure glib2 is on your system.
- flatpak. Of course, this script's entire purpose is for managing flatpak applications, as such, flatpak itself must be installed.

## How to install:
1. Run `printf $PATH` in your terminal.  
2. Download flattool file inside a directory mentioned in "printf $PATH" command with: `wget -P /path/to/bin/directory https://raw.githubusercontent.com/heliguy4599/flattool/main/flattool`
3. Navigate to where you have downloaded the flattool file and run `chmod +x flattool`. This will allow flattool to be executed.


All set! Now all you need to do is run flattool with `flattool --help`.
