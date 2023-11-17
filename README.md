# Linux sine wave device

Based on this awesome book: https://sysprog21.github.io/lkmpg/#character-device-drivers.

Buggy but if you're lucky produces 220Hz sine wave.

Play the sine wave with `play` (part of SoX):

```
play -r 96k -b 32 -e signed-integer -L -c 1 -t raw /dev/sine gain -1
```

## Bugs

The implementation uses `fixp_sin32_rad` from `linux/fixp-arith.h`. This
function performs a division by zero if its second argument (the period
of the sine wave) is less than 360. For a 220Hz sine wave, given our
96kHz sample rate, the period is 436 samples. If you go higher, say to
440Hz, then the period becomes 218 samples, and the module code errors
out because of the division by zero.
