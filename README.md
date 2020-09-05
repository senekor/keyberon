# Keyberon [![Build status](https://travis-ci.org/TeXitoi/keyberon.svg?branch=master)](https://travis-ci.org/TeXitoi/keyberon)

A rust crate to create a pure rust keyboard firmware.

It is exposed as a library giving you the different building blocks to
create a featureful keyboard firmware. As the different functionality
are interconected by the user of the crate, you can use only the parts
you are interested in or easily insert your own code in between.

This crate is a no_std crate, running on stable rust. To use it on a
given MCU, you need GPIO throw the [embedded hal
crate](https://crates.io/crates/embedded-hal) to read the key states,
and the [usb-device crate](https://crates.io/crates/usb-device) for
USB communication.

## Projects using this firmware

The first project using this firmware is [Keyberon
grid](https://github.com/TeXitoi/keyberon-grid), a handwired keyboard
with a grid of keys. It is based on the blue pill, a cheap development
board based on a STM32F103 MCU.

![keyberon-grid](https://raw.githubusercontent.com/TeXitoi/keyberon-grid/master/images/keyberon.jpg)

There is a [port](https://github.com/TeXitoi/ortho60-keyberon) to
[Cannon Keys](https://cannonkeys.com/)'s [Ortho60 keyboard
kit](https://cannonkeys.com/collections/frontpage/products/ortho60).

Another handwired project using keyberon is
[keyberon-f4](https://github.com/TeXitoi/keyberon-f4), a unsplitted
ergo keyboard. It runs on a [WeAct
MiniF4](https://github.com/WeActTC/MiniF4-STM32F4x1) based on a
STM32F401 MCU.

![keyberon-f4](https://raw.githubusercontent.com/TeXitoi/keyberon-f4/master/images/keyberon-56.jpg)

There is also some independant projects that use keyberon. Feel free
to open a PR with your build is you use keyberon!

[TssT16](https://github.com/TssT16)'s 4x12 keyboard:

![TssT16's](https://user-images.githubusercontent.com/12481562/81586297-97996e80-93b5-11ea-86e1-c4358854477e.jpg)

[gilescope](https://github.com/gilescope)'s 4x12 keyboard:

![gilescope's](https://i.redd.it/syvlwmkd77851.jpg)

[covah901](https://www.reddit.com/user/covah901/)'s keyboard:

![covah901](https://i.redd.it/gnkfymu0gwo41.jpg)

## Features

The supported features are:
 - Layers when holding a key (aka the fn key). When holding multiple
   layer keys, the numbers add (if you have a layer 1 key and a layer
   2 key, when holding the 2 together, the layer 3 will be active).
 - Transparent key, i.e. when on a alternative layer, the key have the
   same behavior of the default layer.
 - Change default layer dynamically.
 - Multiple keys send on an single key press. It allows to have keys
   for complex shortcut, as a key for copy and paste, for alt tab, or
   for whatever you want.
 - hold tap: different action depending if the key is holded or
   tapped. For example, you can have a key acting as layer change when
   holded, and space when tapped.
   

## FAQ

### Keyberon, what's that name?

To find new, findable and memorable project names, some persons in the rust community try to mix the name of a city with some keyword related to the project. For example, you have the [Tokio project](https://tokio.rs/) that derive its name from the Japanese capital Tokyo and IO for Input Output, the main subject of this project.

So, I have to find such a name. In the mechanical keyboard community, "keeb" is slang for keyboard. Thus, I searched for a city with the sound [kib], preferably in France as it is the country of origin of the project. I found [Quiberon](https://en.wikipedia.org/wiki/Quiberon), and thus I named the project Keyberon.
