---
title: "The American Keyboard Layout Is the Best"
date: 2019-07-28
tags: ["keyboard", "linux", "i3", "sway", "wayland"]
---

My colleagues (Swedish company) occasionally ask me why I use an American US keyboard layout. Most commonly after quickly trying to type something on my computer and it displaying the wrong characters. The answer is simple. It's better for programming. Editors and programming languages simply feel like they are made with and for the American keyboard layout.

The way your fingers have to move to type characters like \ on a Swedish keyboard (you press AltGr and +) is not very intuitive and it feels like an afterthought. With the American layout, there is a dedicated key, easily accessible and quick to use.

It's even worse for Mac users who use a Swedish layout. The way you type a backslash and other characters are different then on a regular PC keyboard. To type a backslash with a Swedish keyboard on a Mac, you press Alt+Shift+7. That is three keys for one character!

I've seen Mac users trying to type on a PC keyboard, having to manually go through all different number keys while holding different modifier keys. Same goes for people used to a PC keyboard trying to use a Mac. Yes, they can look on the printed characters on the physical keys, but it's not always possible, such as when doing remote desktop.

People might suggest using other alternative keyboard layouts such as [Dvorak](https://en.wikipedia.org/wiki/Dvorak_Simplified_Keyboard), which is designed to fix many problems of a regular QWERTY layout. It might be worth learning it if you type A LOT, but my opinion is that it's not worth ruining your ability to type on other keyboards. Being used to an American layout and typing on a Swedish keyboard only makes it difficult finding the special characters. Being used to Dvorak and typing on QWERTY will make ALL characters difficult to find.

## How?

My native language is Swedish, so I occasionally need to write Swedish characters. The most common way I've seen people do this is by having a hotkey to switch between US and their native layout. The problem is that it's easy to forget which layout you are in and start typing random characters, having to backspace, switch layout and then type it again.

There is an US international layout that some people use, but that alters the behavior of keys like `'` and the key combinations for Swedish characters are spread around the keyboard in what feels like an arbitrary way. This might however be the best option if you write foreign characters from multiple different languages.

My preferred way is to not directly use the `US` layout, but rather use a Swedish layout with the US variant. This makes all keys behave like a regular American keyboard but when AltGr (right alt) is held, the letter keys behave like a Swedish keyboard. They can also be combined with shift to write capital characters.

Only downside to this solution is that special characters missing from the American layout, such as €, is not possible to type. If you have a way of solving this, [please tell me](/contact/)!

I use GNU/Linux without a desktop environment. There might be easier ways to do the same thing with your fancy click-click interface, but this is how I do it.

### i3wm/Xorg
Before going full Wayland on my computers, I used the [i3 window manager](https://i3wm.org). This is what I added to my config then:

`~/.config/i3/config`:
```
exec_always --no-startup-id setxkbmap se -variant us
```

### Sway/Wayland
I currently run [Sway](https://swaywm.org/), which is a tiling Wayland compositor. Input options work a little differently on Sway. They are handled entirely by the compositor, not other programs like setxkbmap. You can set input options on each input individually, and this is how the Sway [wiki](https://github.com/swaywm/sway/wiki#input-configuration) examples do it. I choose to instead use a wildcard as an identifier to apply the layout on all keyboards, instead of individual inputs.

This is what I add to my Sway config:

`~/.config/sway/config`:
```sh
input * {
  xkb_layout se
  xkb_variant us
}
```
