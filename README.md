# SAO-display

A modular system for displaying
[Shitty Add-Ons](https://hackaday.com/2019/03/20/introducing-the-shitty-add-on-v1-69bis-standard/)
on a wall, with their lights a-blinkin'.

Points:
- hexagonal mocules, for arbitrary tiling
- magnetic pogo-pin connectors for power distribution
- a buck converter on each module to minimise power loss through pogo pins
- space for art
- 3D-printed surrounds

Some design history:
- Originally all 6 pogo pin connectors had identical polarity ...
until I powered up the first board, and connected it to the second.
Magic smoke was released from the second board's buck converter,
because it had been fed -12V rather than +12V.

- So, the pogo pin connectors now alternate in polarity,
so that when multiple boards are connected together,
if all are oriented the same way, their +12V and 0V lines will
only make electrical contact like with like.

- But if a board was not correctly oriented we would still have a
problem with reverse polarity connection.

Non-zener diode protects buck converter module from reverse-polarity supply.

Zener diode protects buck converter from over-voltage supply.

Resistor protects zener diode from reverse-polarity supply.

The previous iteration of this board did not include the resistor;
if you have some of those, you should retro-fit a resistor in series
with the zener diode, between the supply voltage line and ground.
The value is not critical, but something around 800 Ohms will ensure
the fault current through the zener stays relatively low, in the event
of reversed power supply connection.

