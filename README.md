# EDWM

Enhanced Dynamic Window Manager.

Added functionalities based on the original [Dynamic Window Manager (DWM)](https://dwm.suckless.org/) to make things much easier. Thanks suckless guys, a lot!

I've been using `DWM` for over 4 years, simple things keeps your mind focused on what you're doing. Since the publish of 6.4, I arranged another upgrade and added some other functionalities and features that I think will make life beautiful. I'll list them in the following sections.

I don't really use the tiling system much becuase of the existence of tmux. But I've come up with that the `tile` system introduced by `DWM` can be very much used to implement a `task view` (I call it `Deep View`) functionality. During the years of using DWM, I found myself seldomly swithing beyond three (3) tags, because you know, switching tags is a kind of overhead, I might as well have multiple windows open in one tag, and have a way to find each window quickly is enough. And if I do need to swith tags, only because I have too many windows open in one..., that rarely happens because I have multiple monitors connected.

That being said, the goal is to:

* Easily find a window if there're many opened in the same tag;
* Easily maximize a window without using the `Monocle` feature of the original DWM;
* Have indicators of how many windows are opened in the current tag;

That being said, hopefully you will find the following enhancements handy.

# Features

## Deep View

All windows defaults to open floating, so the tile system won't kick in to resize the unfocus windows. Assuming you have multiple windows opened in one tag, to find a particular window easily, go into `Deep View` (default key combination is `Mod + XK_d`), this will clear all the floating bits of windows and let the tile system arrange them on the screen, so you can choose whichever window you want to interact with by simply click on it. Easy! And to exit `Deep View`, just press the same key combination again, everything restores to their original size and position, nothing happend.

Note that in EDWM the default layout has been changed to floating, the layout symbol being `><>`, I like this little fish.

Note that when in `Deep View` mode, the layout symbol is `[D]`, so that you know where you're.

Note that at present you cannot click on the window that's already been focused to exit `Deep View`, I'll figure it out later, but I don't think it's going to matter much, becuase you just press `Mod + XK_d` again and everyhing's good.

## Maximize a Window

Being able to maximize a window is crucial, the original `Monocle` mode is not that ideal. So now, press `Mod + XK_f` to maximize a window, and `Mod + XK_f` again to bring the window back to its original position and size.

Note that the maximized window is doesn't cover the status bar, to perform an actual full screen, hit `Fn + F11` if the window supports it.

## Indocator of Number of Windows Opened

One thing about floating layout is that if some windows are hiding behind the current one, it's hard to tell how many windows are there in current tag. So I added this indicator to show me the number of windows opened in a particular tag, so I know there're multiple windows, then I can use `Deep View` to find the one I want.

You don't have to note anything, it's just a number :D

## Community Patches

I've applied some patches so that:

* The status bar will be on every monitor connected;

# Installation

Rename `sample.config.mk.xxx` to `config.mk` according to the system you're on.

Then `make && sudo make install clean` to compile and install.

That's it! Enjoy!

# Default Key Combinations and Functionalities

Listed below are the changed key combinations different from the original implementation.

|Key Comb|Function|
|:------:|:------:|
|Mod + XK_Tab|Cycle through windows (clockwise)|
|Mod + Shft + XK_Tab|Cycle through windows (counter clockwise)|
|Mod + XK_d|Toggle deep view|
|Mod + XK_f|Toggle maximize a window|
|Mod + XK_g|Spawn dmenu|
|Mod + XK_a|Spawn xterm (refer to dwm.c, spawnxterm function)|
|Mod + XK_v|Minimize a window to lower right corner of screen (maybe buggy), again to restore|
|Mod + XK_c|Kill client|
|Mod + XK_bracketright|Quit DWM|
|Middle Mouse Button|Move window|
|Mod + Right Mouse Button|Resize window|

For a complete key combination, refer to `config.def.h`, feel free to modify.

# Bugs

For any bugs found, open an issue and I'll have it fixed if time permits.

# Credits

* [Suckless DWM](https://dwm.suckless.org/)
