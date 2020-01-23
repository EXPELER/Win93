
<a name="index"/>

# Index

<!--ts-->
* [Installing Win93](#install_theme)
* [Installing Openbox](#install_openbox)
    * [Installing Openbox-theme](#install_openbox-theme)
* [Desktop-Styling](#desktop-styling)
* [Installing Fonts](#install_fonts)
* [Replacing GTKRC](#replace_gtkrc)
* [Replacing GTK.css](#replace_gtkcss)
* [Installing Panel](#install_panel)
* [Installing Plymouth](#install_plymouth)
* [Installing Lightdm-Webkit-Greeter](#install_lightdm)
* [Installing Terminal](#install_terminal)
* [Startup-Sound](#install_sound)
<!--te-->

---
<a name="install_theme"/>

## Installing Win93


### First make sure to install Chicago95 (https://github.com/grassmunk/Chicago95) 

<a name="install_openbox"/>

### Installing new Icons

- Move the folders in `~/Win93-master/Replace/Icons/` to `~/.icons/Chicago95/apps/` and select replace all.
- Move Starticon.png in `~/Win93-master/` to `~/.Icons` 

### Installing Openbox

(warning this will replace your default window manager!)

#### Step 1: install openbox

`sudo apt-get install openbox obconf`

#### Step 2: Make openbox autostart at startup
- go to XFCE settings manager > Session and Startup > Application Autostart
- Click `add` and fill in

`name:"openbox"`

`Description:"window-manager"`

`Command:"openbox --replace"` 

(this will replace your window-manager at startup with openbox).
- now reload the desktop (your window manager should be changed).

<a name="install_openbox-theme"/>

### [ Installing Openbox-theme ]

#### Step 1: Copy the Win93-Openbox 

- Copy the Win93-Openbox folder in `~/Win93-master/Openbox/` to `~/.themes`

#### Step 2: Configuring Openbox
- Open the Openbox Configuration Manager
- Select Win93-Openbox.

<a name="desktop_styling"/>

### Desktop-Styling

#### Step 1: Change the desktop background 

- go to desktop settings.. (right click on desktop)
- put style to none and the color to horizontal gradient `#f0f` to `#0ff`

#### Step 2: Desktop icon size

- Go to Desktop Settings.. > Icons and put the size to 32.

<a name="install_fonts"/>

### Installing Fonts

#### Step 1: Install the fonts

- Install the M8pt.ttf, basis33.ttf and px_sans_nouveaux.ttf  located in the Win93-master folder.

#### Step 2: Setting up the fonts in XFCE

- Open the XFCE settings manager > Appearance > fonts. 
- Make the default font "pix M 8pt" with the letter size 6.
- Make the monospacefont "basis33" with the letter size 6.

#### Step 3: Setting up the fonts in Openbox

- Open the Openbox Configuration Manager > appearance 
- Make all the fonts "px_sans_nouveaux" and put it on size 6.

#### Step 4: Setting up the fonts in qt5ct

- Open qt5ct type `qt5ct` in terminal 
- Make all the fonts "px_sans_nouveaux" and put it on size 6.

<a name="replace_gtkrc"/>

### Replacing GTKRC

- Move the gtkrc in `Win93-master/Replace/GTK/` folder to `~/.themes/Chicago95/gtk-2.0/` 
- Reboot

<a name="replace_gtkcss"/>

### Replacing GTK.css

- Move the GTK.css in `Win93-master/Replace/GTK/` folder to `~/.themes/Chicago95/gtk-3.0/`
- Reboot
<a name="install_panel"/>

### Installing Panel

- Open the XFCE settings manager > Panel
- Make the Panel row size 26.
- select the whiskers menu and click on minus.
- Click on the plus and search for "Application Menu"
- Move the applications menu to the top.
- Open the applications menu by clicking on it.
- Unmark "show button title"
- change the icon for "starticon.png" in the .icons directory
- open the window buttons menu and unmark show handle.
- open orange panel clock and put this in line 1 include the spaces!! `"      %H:%M      "`(you might open this file with notepad to see the spaces.

<a name="install_plymouth"/>

### Installing Plymouth

- Move the plymouth folder in `~/Win93-master/Plymouth/` to `/usr/share/plymouth/themes/`
- now open terminal and write `sudo update-alternatives --install /usr/share/plymouth/themes/default.plymouth default.plymouth /usr/share/plymouth/themes/win93/win93.plymouth 100`
- Select the default theme `sudo update-alternatives --config default.plymouth` And select the number with win93.
- Update the initramfs image `sudo update-initramfs -u`
- reboot

<a name="install_lightdm"/>

### Installing Lightdm-Webkit-Greeter

- Install lightdm with `sudo apt-get install lightdm lightdm-webkit-greeter`
- move the folder from `~/Win93-master/Lightdm/` to `/usr/share/lightdm-webkit/themes/` (dont forget to change the permissions to read and write of the lightdm-webkit folder, otherwise you get locked out your system!!!!!!!!!!!)
- Open terminal and type `sudo nano /etc/lightdm/lightdm.conf`
- and change it to

```
[SeatDefaults]
greeter-session=lightdm-webkit-greeter
user-session=xfce
```

- Save and exit
- Now type `sudo nano /etc/lightdm/lightdm-webkit-greeter.conf` and set the "theme-name" and "webkit-theme" to "Win93"
- Save and exit 

<a name="install_terminal"/>

### Installing Terminal

#### Step 1: Setting up Bashrc

- Go to `~/home/` and open the `.bashrc`
- add the code from `~/win93-master/terminal.txt` under the "fi" in the `.bashrc`

#### Step 2: Setting up Terminal appearance
- Open the terminal (Ctrl - Alt + T)
- Open edit > preferences > Appearance
- Change the font to "basis33 Regular" size 13.
- Make the default geometry to 50 and 17 rows.
- Open edit > preferences > Colors 
- make the text color to `#c3ff00` and the background color to `#000000`
- make the text selection color to `#000000` and `#c3ff00`
- make the bold text `#24FF00`

<a name="install_sound"/>

### [ Windows 93 login startup sound ]
- installed sox
`sudo apt install sox`
- copy the file `Win93-master/win93.ogg` to `~/.themes/Chicago95/misc/win93.ogg`.



