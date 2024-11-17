# KDE Service Menus for Video File Conversion

Easily convert video files to popular formats like MP4 or WebM using KDE service menus. The encoding settings are optimized for broad compatibility and a good balance between encoding speed and file size.

Conversion is performed using **FFmpeg**. If available, hardware encoding with **VAAPI** will be used for enhanced performance.

---

## Prerequisites

Ensure the following tools are installed:

- [KDE](https://www.kde.org/)  
- [FFmpeg](https://ffmpeg.org/)  
- [BC](https://www.gnu.org/software/bc/)  

### For hardware encoding support on Intel CPUs:

- [Intel Media Driver](https://01.org/linuxmedia)  
- [libva-intel-driver](https://github.com/intel/libva)  
- [libva-utils](https://github.com/intel/libva-utils)  

---

## Installation (Plasma 6)

### Install Dependencies (Arch Linux)

Run the following command to install the required tools:

```bash
sudo pacman -S ffmpeg qt6-tools bc
```

For hardware encoding support on Intel CPUs, install:

```bash
sudo pacman -S intel-media-driver libva-intel-driver libva-utils
```

### System-Wide Installation

Copy the necessary files to the system directories:

```bash
sudo cp servicemenus/* /usr/share/kio/servicemenus/
sudo cp bin/videoconvert-kdialog /usr/local/bin/
```

### Per-User Installation

For a user-specific setup, copy the files as follows:

```bash
cp servicemenus/* ~/.local/share/kio/servicemenus/
cp bin/videoconvert-kdialog ~/.local/bin
```

Make sure the `~/.local/bin` directory is included in your `$PATH` environment variable.  
Additionally, set the `.desktop` files to be executable:

```bash
chmod +x ~/.local/share/kio/servicemenus/videoconvert.desktop
```

Finally, restart your Plasma session or run the following command:

```bash
kbuildsycoca6
```

---

## Uninstallation

### System-Wide Uninstallation

Remove the installed files:

```bash
sudo rm /usr/share/kio/servicemenus/videoconvert.desktop
sudo rm /usr/local/bin/videoconvert-kdialog
```

### Per-User Uninstallation

Delete the corresponding files:

```bash
rm ~/.local/share/kio/servicemenus/videoconvert.desktop
rm ~/.local/bin/videoconvert-kdialog
```

---

## Contributing

We welcome contributions! Please follow these guidelines:

- For major changes, open an issue first to discuss your ideas.
- Ensure any necessary tests are updated appropriately.

Pull requests are encouraged and appreciated.

---

## License

This project is licensed under [GPL-3.0+](https://www.gnu.org/licenses/gpl-3.0.html).
