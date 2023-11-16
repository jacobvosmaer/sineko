# Linux sine wave device

Based on this awesome book: https://sysprog21.github.io/lkmpg/#character-device-drivers.

Buggy but if you're lucky produces 220Hz sine wave.

Play the sine wave with `play` (part of SoX):

```
dd if=/dev/sine bs=4 count=500000 | play -r 96k -b 32 -e signed-integer  -L -c 1 -t raw - norm -2
```
