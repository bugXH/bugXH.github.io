---
layout: post
title: Remap the CapsLock key to left Control
---
The left Control key on my laptop doesn't work very responsively lately. So I want to map another key to left Control key. I managed to find some nice tutorials about swapping two keys with Xmodmap:

[Swapping the left Alt and Control keys](https://earthviaradio.wordpress.com/2012/02/06/swapping-the-left-alt-and-ctrl-keys-in-ubuntu-11-10/)

[Swapping the CapsLock and left Control key](http://www.cnblogs.com/lzhskywalker/archive/2012/07/20/2600854.html)

Actually I don't really need to functionality of CapsLock. So I just wanted to map my CapsLock key to left Control. Based on this [site](http://unix.stackexchange.com/questions/114022/map-caps-lock-to-control-in-linux-mint). 

Add the following to **~/.xmodmap**:

{% highlight shell%}
remove Lock = Caps_Lock
keysym Caps_Lock = Control_L
add Control = Control_L
{% endhighlight %}

run: **xmodmap ~/.xmodmap** (effective temporarily) or just log out and log back in

If doesn't work, add the following to **~/.xinitrc**:

{% highlight shell%}
if [ -f $HOME/.Xmodmap ]; then
  /usr/bin/xmodmap $HOME/.Xmodmap
fi
{% endhighlight %}

Based on this [site](http://askubuntu.com/questions/321510/set-context-menu-key-to-function-as-right-control)

Issues:

* If the laptop wakes up from sleep, the mapping doesn't work. Needs to log out and log back in to enable to new mapping

* The script added in **~/.xinitrc** will cause a "login loop" after reboot