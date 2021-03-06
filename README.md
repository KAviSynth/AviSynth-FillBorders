# Description

This is a simple filter that fills the borders of a clip, without changing the clip's dimensions.

This is [a port of the VapourSynth plugin FillBorders](https://github.com/dubhater/vapoursynth-fillborders).

# Usage

```
FillBorders (clip, int "left", int "top", int "right", int "bottom", int "mode", int "y", int "u", int "v")
```

The additional function FillMargins is alias for FillBordes(mode=0).

```
FillMargins (clip, int "left", int "top", int "right", int "bottom", int "y", int "u", int "v")
```

## Parameters:

- clip\
    A clip to process. All planar formats are supported.

- left, top, right, bottom\
    Number of pixels to fill on each side. These can be any non-negative numbers, within reason. If they are all 0, the input clip is simply passed through.\
    Default: left = top = right = bottom = 0.

- mode (FillBorders only)\
    0: "fillmargins"\
        Fills the borders exactly like the Avisynth filter FillMargins, version 1.0.2.0. This mode is similar to "repeat", except that each pixel at the top and bottom borders is filled with a weighted average of its three neighbours from the previous line.\
    1: "repeat"\
        Fills the borders using the outermost line or column.\
    2: "mirror"\
        Fills the borders by mirroring.\
    Default: 0.

- y, u, v\
    Planes to process.\
    1: Return garbage.\
    2: Copy plane.\
    3: Process plane. Always process planes when the clip is RGB.\
    Default: y = u = v = 3.
