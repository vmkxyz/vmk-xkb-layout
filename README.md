# Before you Read
The documention is still a work in progress.<br>
For now Linux only, uses the X11 xkb system (which you can use on wayland).<br>
Note: The right alt key, aka 'AltGr' will be refered to as 'RAlt' in the documentation.<br>

# About This Project
This project is a collection of keyboard layouts mainly targeted for people who prefer the US keyboard layout but need to write czech diacritics. While not inspired by it, it has a similar goal to the [czech coder layout](https://github.com/michalkahle/czech-coder-xkb) made by [Michal Kahle](https://github.com/michalkahle), however, this is a standalone layout with multiple variants in it reather the a single variant of the Czech layout.

# Layout Variants
The layout currently features 2 variants:
* default: Allows you to type Czech diacritics with RAlt and type Greek letters with RAlt+Shift, also adds a lot of other characters (see [layout images](readme/vmk_default/)).
* nobloat: Only has Czech diacritics added under RAlt, nothing else (see [layout images](readme/vmk_nobloat)).

# How to Use
1.  Clone this repo: `git clone https://github.com/vmkxyz/vmk-xkb-layout.git`
2.  Copy the layout to the `/usr/share/X11/xkb/symbols/` directory: `sudo cp vmk-keyboard-layout/vmk /etc/share/X11/xkb/symbols/vmk`
3.  Reboot
4.  Set your keyboard layout to 'vmk' and chose your variant.

that should work, havent tested it much tho

# Q&A
Q: How do I change my keyboard layout?<br>
A: On a DE, find it in settings, on Xorg WMs I think you use the `setxkbmap` command; wayland WMs each have differend ways of setting it, just read their documentation.

Q: Why is the layout called 'vmk'?<br>
A: First half of my github username, maybe I'll change the layout name in the future, I just didn't know what to call it.

Q: Will you make more variants?<br>
A: Most likely, submit a request in github issues if you wnat anything specific.

Q: Will you port the vmk layout to other OSes?<br>
A: I am working on windows one and might do other ones in the future

Q: I want to make my own layout too.<br>
A: I am going to write a markdown file describing the process of making your own keyboard layout or editing other ones, it will be in this repo when its done.

# Other Stuff
The [czech coder layout](https://github.com/michalkahle/czech-coder-xkb) by [Michal Kahle](https://github.com/michalkahle) is a cool project and might be all you need, go check it out.<br>
Tested on Arch Linux, Hyprland.<br>
Layout screenshots made in Gnome Tecla.<br>
If your system can't find the layout, try putting this into `/usr/share/X11/xkb/rules/evdev.xml`:
````
    <layout>
      <configItem>
        <name>vmk</name>
        <!-- Keyboard indicator dor vmk layouts -->
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
