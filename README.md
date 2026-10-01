This is a guide to running Simple Mod Framework on Linux under Proton, previously we would try to add it as a non steam game, you do not need to do this anymore. 
this assumes your steam location is in ~/.local/share/Steam , and that you have installed Proton-GE Latest

First go to https://github.com/atampy25/simple-mod-framework and download the latest release.zip,
open a terminal and run 7z x ~/Downloads/Release.zip -oDownloads/Release/ 

Which will extract the contents into the folder named Release, 

rename Release/ to "Simple Mod Framework" using

$ mv ~/Downloads/Release/ "/home/YOURUSER/Downloads/Simple Mod Framework/"

move this folder into HITMAN 3 steam install. 

$ mv "/home/YOURUSER/Downloads/Simple Mod Framework" "/home/YOURUSER/.local/share/Steam/steamapps/common/HITMAN 3/"
 
That is simple mod framework installed. 

I have included a desktop entry with preconfigured paths for Proton-GE Latest and the executable, please replace every instance of YOURUSER with your linux username.

Notes -
If running Peacock on Linux too, it cannot detect SMF's lastDeploy.json file

your lastDeploy.json will be located after mod deployment is done in this path
"/home/YOURUSER/.local/share/Steam/steamapps/compatdata/1659040/pfx/drive_c/users/steamuser/AppData/Local/Simple Mod Framework/lastDeploy.json"

in order for Peacock on Linux to read it, please do the following

$ mkdir -p ~/.local/share/app.simple-mod-framework

and then symlink 

$ ln -s "/home/YOURUSER/.local/share/Steam/steamapps/compatdata/1659040/pfx/drive_c/users/steamuser/AppData/Local/Simple Mod Framework/lastDeploy.json" "/home/YOURUSER/.local/share/app.simple-mod-framework/"

a tilda or ~ denotes home directory which cannot be parsed with quotation marks so just be aware when executing commands, since Simple Mod Framework has whitespace in its directory name, it's easier quoting the full path"
