# Before you Read
The documentation is still a work in progress.<br>
Linux and Windows versions availbale<br>
Note: The right alt key, aka 'AltGr' will be referred to as 'RAlt' in the documentation.<br>

# About This Project
This project is a collection of keyboard layouts mainly targeted at people who prefer the US keyboard layout but need to write czech diacritics. While not inspired by it, it has a similar goal to the [czech coder layout](https://github.com/michalkahle/czech-coder-xkb) made by [Michal Kahle](https://github.com/michalkahle), however, this is a standalone layout with multiple variants in it reather then a single variant of the Czech layout.

# Layout Variants
The layout currently features 2 variants:
* default: Allows you to type Czech diacritics with RAlt and type Greek letters with RAlt+Shift, also adds a lot of other characters (see [layout images](readme/vmk_default/)).
* nobloat: Only has Czech diacritics added under RAlt, nothing else (see [layout images](readme/vmk_nobloat)).

Note: only nobloat is currently available for windows.

# How to Use - Linux
1.  Clone this repo: `git clone https://github.com/vmkxyz/vmk-xkb-layout.git`
2.  cd into there: `cd vmk-xkb-layout`
3.  Copy the layout to the /usr/share/X11/xkb/symbols/ directory: `sudo cp vmk /usr/share/X11/xkb/symbols/vmk`
4.  Reboot
5.  Set your keyboard layout to 'vmk' and choose your variant.

# How to Use - Windows (binary)
1.  Download this repo as a zip and extract it (or clone it).
2.  Open the vmk_win folder.
3.  Open the folder of the layout you want to use.
4.  Run setup.exe

# Want to compile the Windows binary yourself?
1.  [Download MSKLC](https://download.microsoft.com/download/6/f/5/6f5ce43a-e892-4fd1-b9a6-1a0cbb64e6e2/MSKLC.exe)
2.  Download this repo as a zip and extract it (or clone it).
3.  Open MSKLC, press ctrl+o or go to File > Load Dource File...
4.  Go to vmk_win and choose the .klc file of the layout you want to use.
5.  In MSKLC, go to Project > Build DLL and Setup Package
6.  Run the compiled setup.exe

# Q&A
Q: Why is the layout called 'vmk'?<br>
A: First half of my github username.

Q: Will you make more variants?<br>
A: Yes.

Q: Will you port the vmk layout to other OSes?<br>
A: Probably macos.

# Other Stuff
* vmk_nb stands for vmk_nobloat, Windows just doesn't like long names.
* The [czech coder layout](https://github.com/michalkahle/czech-coder-xkb) by [Michal Kahle](https://github.com/michalkahle) is a cool project and might be all you need, go check it out.<br>
* Linux version tested on Arch Linux, Hyprland.<br>
* Windows version tested on Windows 11, binary should work on Win10 too, for older versions, I recommend compiling it yourself.
* Layout screenshots made in Gnome Tecla.<br>
* I think the Linux version should work no BSDs too, I don't have any experience with them tho.

# Troubleshooting
If your system can't find the layout, try putting this into `/usr/share/X11/xkb/rules/evdev.xml` and then reboot:
````
    <layout>
      <configItem>
        <name>vmk</name>
        <!-- Keyboard indicator for vmk layouts -->
        <shortDescription>vmk</shortDescription>
        <description>vmk Custom Layout</description>
        <languageList>
          <iso639Id>eng</iso639Id>
	</languageList>
      </configItem>
      <variantList>
        <variant>
	  <configItem>
	    <name>nobloat</name>
	    <description>US layout with czech diacritics under RAlt, nothing more than that</description>
	  </configItem>
	</variant>
      </variantList>
    </layout>
````

As far as I know, you can only have one custom keyboard layout on Windows at a time, so if you want to use another one, delete the previous.
