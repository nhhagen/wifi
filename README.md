# Wifi

![image](http://i.imgur.com/mEEPD.png)

Wifi is a little bash script that uses [Spark](https://github.com/holman/spark)
to display the wifi status on your __tmux__ sessions or the __terminal__.

This is a fork of [Battery](https://github.com/Goles/Battery) and adapted to
display wifi signal strength.

### Features

* Changes color to reflect wifi status (Green, Yellow, Red)
* Displays wifi percentage
* Graph bar changes its values between 0 and 100% (thanks to spark)
* If you don't like the default colors, you can specify the good, medium and
    warning wifi status colors using flags (read usage).

### Requirements

Right now, wifi requires [Spark](https://github.com/holman/spark) to graph your
wifi status. Wifi can run on __Mac OS X__

If you don't want to use Spark, you can use the `-a` flag, for ascii output:
![image](http://i.imgur.com/w9qtQeu.png)

# Install - Mac

### Homebrew (Does now work yet, I think)

Just do (case sensitive)

    brew tap nhhagen/wifi
    brew install wifi

### One Liner
(Cut & Paste on terminal to install on `/usr/bin`, btw, try to run from `~/` or
other writable dir)

	brew install spark; curl -O https://raw.github.com/nhhagen/Wifi/master/wifi ; \
	sudo mv wifi /usr/bin; sudo chmod 755 /usr/bin/wifi


### Step by Step

* Install spark (with [Homebrew](https://github.com/mxcl/homebrew) on Mac OS X)

	``` brew install spark```

* Copy wifi somewhere in your path & fix permissions

	``` sudo cp wifi /usr/bin ```

	``` sudo chmod 755 /usr/bin/wifi ```

# Usage

### Terminal

* Run Wifi (From the terminal)

	``` wifi ```
###### You should see something like this:
![image](http://i.imgur.com/SLSBg.png)

### tmux

* Be sure to make tmux display utf-8 characters by running it with the `-u` flag

	```tmux -u```

* Add the following line to your `~/.tmux.conf` file

	``` set -g status-right "#(/usr/bin/wifi -t)"```

* reload the tmux config by running `tmux source-file ~/.tmux.conf`.

###### You should now see something like this at the bottom right corner:
![image](http://i.imgur.com/Eaajb.png)

# Flags

You can specifiy the colors for __good__ wifi
level, __middle__ wifi level, and __warning__ wifi level with the flags `-g
-m -w`.  __Note:__ You should use color names for when in tmux mode and
[ascii colors](http://www.termsys.demon.co.uk/vtansi.htm#colors) in terminal
mode.
