# Before you Read
The documentation is still a work in progress.<br>
For now Linux only, uses the X11 xkb system (which you can use on wayland).<br>
Note: The right alt key, aka 'AltGr' will be referred to as 'RAlt' in the documentation.<br>

# About This Project
This project is a collection of keyboard layouts mainly targeted at people who prefer the US keyboard layout but need to write czech diacritics. While not inspired by it, it has a similar goal to the [czech coder layout](https://github.com/michalkahle/czech-coder-xkb) made by [Michal Kahle](https://github.com/michalkahle), however, this is a standalone layout with multiple variants in it reather then a single variant of the Czech layout.

# Layout Variants
The layout currently features 2 variants:
* default: Allows you to type Czech diacritics with RAlt and type Greek letters with RAlt+Shift, also adds a lot of other characters (see [layout images](readme/vmk_default/)).
* nobloat: Only has Czech diacritics added under RAlt, nothing else (see [layout images](readme/vmk_nobloat)).

# How to Use
1.  Clone this repo: `git clone https://github.com/vmkxyz/vmk-xkb-layout.git`
2.  cd into there: `cd vmk-xkb-layout`
3.  Copy the layout to the /usr/share/X11/xkb/symbols/ directory: `sudo cp vmk /usr/share/X11/xkb/symbols/vmk`
4.  Reboot
5.  Set your keyboard layout to 'vmk' and choose your variant.

That should work, haven't tested it much tho

# Q&A
Q: Why is the layout called 'vmk'?<br>
A: First half of my github username; maybe I'll change the layout name in the future, I just didn't know what to call it.

Q: Will you make more variants?<br>
A: Most likely, submit a request in GitHub issues if you want anything specific.

Q: Will you port the vmk layout to other OSes?<br>
A: I am working on a Windows one and might do other ones in the future.

# Other Stuff
The [czech coder layout](https://github.com/michalkahle/czech-coder-xkb) by [Michal Kahle](https://github.com/michalkahle) is a cool project and might be all you need, go check it out.<br>
Tested on Arch Linux, Hyprland.<br>
Layout screenshots made in Gnome Tecla.<br>

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
I didn't run into any other issues yet
