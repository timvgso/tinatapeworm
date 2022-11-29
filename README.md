![](../../workflows/gds/badge.svg) ![](../../workflows/docs/badge.svg)

# Worm in a Maze

Worm in a Maze is a digital electronic project submitted to [Tiny Tapeout](https://tinytapeout.com/)
hat shows an animation of a segmented worm traveling on a pseudo-random path. The worm is shown
on the seven-segment LED of the Tiny Tapeout breakout board and moves through a figure-eight course.

The circuit was designed using the Wokwi website and can be seen at https://wokwi.com/projects/348381622440034899.

![screen](https://user-images.githubusercontent.com/54959859/203157420-dc917ee6-395d-45fd-9586-eaab93f7827c.png)

## Using

Click the "play" button on the Wokwi page to start the simulation of the circuit. Make sure
that the slide switch above the "Digital Input" block is in the left position, selecting the 25 Hz clock.
Depending on the speed of your machine, the animation might run somewhat slower than real-time.
(There are a lot of logic gates in the circuit to be simulated.)

To chenge the settings, clock on the red 8-position DIP switch and toggle switch as detailed below.
The 1-8 keyboard keys can be used to change switch positions once the switch device is selected.

## Controls

Worm in a Maze includes digital logic to detect when the state of the display is invalid
and automatically generates a reset signal when this is detected. This auto-reset can be
disabled by changing digital input 1 (DIP switch #2) to the On position.
Digital input 2 (DIP switch #3) is a manual reset.
Move it to the On position and then back to Off to force a reset.

Worm in a Maze was designed to operate the maximum clock divider of 255 available on the
breakout board. With an expected serial bit rate of 12500 Hz and thus a clock of 6250 Hz,
digital input 0 will see a clock rate of about 25 Hz. A set of logic gates further divides
this clock rate by 16 so that the LED display updates at a rate of between once and twice
per second. DIP switch #4 ("turbo switch") bypasses this clock divider, primarily for
convenience when single-stepping the circuit for debugging or demonstrating.

Digital input 4 (DIP switch #5) selects the number of worm segments shown on the LED display.
In the Off position, two segments are shown. In the On position, three segments are shown.
Depending on [persistence of vision](https://en.wikipedia.org/wiki/Persistence_of_vision)
and the clock rate available and perhaps some other factors, one or the other might be more
effective and enjoyable when the actual hardware is available.

Digital input 5 (DIP switch #6) disables the pseudo-random binary input that controls
path decisions at 3-way junctions. When this switch is in the On position, digital input 6
(DIP switch #7) can be used to manually control the path decisions at junctions.
The Off switch position generates the same decisions as a 0 bit from the pseudo-random-number
generator would. The On switch position is equivalent to a 1 bit.
