# Simple Mod Framework on Linux (Proton)

A guide to running Simple Mod Framework (SMF) on Linux under Proton without adding it as a non-Steam game.

## Prerequisites

- Steam installed with standard location: `~/.local/share/Steam`
- [Proton-GE Latest](https://github.com/GloriousEggroll/proton-ge-custom) installed
- HITMAN 3 installed via Steam
- `7z` utility installed for extraction

## Installation

### Step 1: Download Simple Mod Framework

Download the latest release from the [official repository](https://github.com/atampy25/simple-mod-framework):

```bash
cd ~/Downloads
wget https://github.com/atampy25/simple-mod-framework/releases/download/[VERSION]/Release.zip
```

### Step 2: Extract the Archive

Extract the release archive to your Downloads folder:

```bash
7z x ~/Downloads/Release.zip -oDownloads/Release/
```

### Step 3: Rename the Folder

Rename the extracted folder to "Simple Mod Framework":

```bash
mv ~/Downloads/Release/ ~/Downloads/Simple\ Mod\ Framework/
```

### Step 4: Move to HITMAN 3 Installation

Move the folder to your HITMAN 3 Steam directory:

```bash
mv ~/Downloads/Simple\ Mod\ Framework/ ~/.local/share/Steam/steamapps/common/HITMAN\ 3/
```

**Installation complete!**

## Desktop Entry (Optional)

A preconfigured desktop entry is included in this repository. To use it:

1. Open the `.desktop` file in a text editor
2. Replace all instances of `YOURUSER` with your Linux username
3. Place the file in `~/.local/share/applications/`

## Peacock Integration (Optional)

If you're also running Peacock on Linux, you'll need to create a symlink so Peacock can access SMF's `lastDeploy.json` file.

### Step 1: Create the Application Directory

```bash
mkdir -p ~/.local/share/app.simple-mod-framework
```

### Step 2: Create a Symlink

After deploying a mod with SMF, create a symlink to the `lastDeploy.json` file:

```bash
ln -s ~/.local/share/Steam/steamapps/compatdata/1659040/pfx/drive_c/users/steamuser/AppData/Local/Simple\ Mod\ Framework/lastDeploy.json \
  ~/.local/share/app.simple-mod-framework/lastDeploy.json
```

The `lastDeploy.json` file is created in this Proton prefix path after you deploy your first mod.

## Important Notes

- **Tilde expansion (`~`)**: The tilde character denotes your home directory and cannot be used within quotation marks. Use `~/` instead of `~` when specifying paths in quotes.
- **Spaces in paths**: Since "Simple Mod Framework" contains spaces, be sure to escape them with backslashes (`\ `) or use quotes around the entire path.
- **Peacock compatibility**: Peacock on Linux cannot automatically detect SMF's deployment data without the symlink workaround described above.

## Troubleshooting

If you encounter issues:

1. Verify your Steam path is correct: `ls ~/.local/share/Steam/steamapps/common/HITMAN\ 3/`
2. Ensure Proton-GE Latest is properly installed
3. Check that all permissions are correct on the SMF folder
4. Review the Peacock symlink path if using Peacock integration

## Resources

- [Simple Mod Framework](https://github.com/atampy25/simple-mod-framework)
- [Proton-GE](https://github.com/GloriousEggroll/proton-ge-custom)
- [Peacock on Linux](https://github.com/thepeacockproject/linux-steam-setup)
