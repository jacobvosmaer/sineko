# Linux sine wave device

Based on this awesome book: https://sysprog21.github.io/lkmpg/#character-device-drivers.

Buggy but if you're lucky produces 220Hz sine wave.

Play the sine wave with `play` (part of SoX):

```
play -r 96k -b 32 -e signed-integer -L -c 1 -t raw /dev/sine gain -1
```
