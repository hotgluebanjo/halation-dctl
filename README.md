# Halation

Pretty good halation.

<img src="https://user-images.githubusercontent.com/66244111/189506168-e3f76389-cc62-43a9-81aa-791410cc1c14.jpg" width="49%"/> <img src="https://user-images.githubusercontent.com/66244111/189506155-1442e07a-8c76-4552-8bd8-4032dd8d0beb.jpg" width="49%"/>
<img src="https://user-images.githubusercontent.com/66244111/189506175-b8edb7e5-556d-47e5-982d-8e3209e850c6.jpg" width="49%"/> <img src="https://user-images.githubusercontent.com/66244111/189506146-9db18f9e-df64-4840-8b65-b1f78771d2fd.jpg" width="49%"/>

## Features

- Exponential falloff - Not just a Gaussian blur.
- Physically accurate - Maybe not totally correct, but it does tend to behave very well.
- Tweakable

There are two included methods. Neither use Sobel or a similar edge detection algorithm.

## Usage

**If a transfer function is present, remove it**. The DCTL requires scene-linear values. Use the Colorspace Transform OFX plugin if your curve is supported.

Apply via the DCTL OFX plugin.

## FAQ (probably)

### I barely notice it.

The default size is set small for speed. Be aware that halation is naturally subtle. If its effect is more minimal than expected, even with a larger size, there's a good chance *your image isn't actually that high contrast* and its response is realistic.

### It's blurring the rest of my image.

Slight softening of the rest of the frame isn't necessarily inaccurate. Halation is much more prominent around high contrast edges but isn't strictly relegated to them. Removing halation from a film image is a good way to observe this.

### Why not $other_method?

Nearly every nonproprietary halation algorithm has one or more of the following problems:

- Bad falloff. Often from a Gaussian or box blur. Sometimes there is a [banding problem](https://youtu.be/tPkaqZjeDTE?t=227) where the dissipating area is split into two color swaths.
- Excessive highlight tinting.
- Overzealous edge detection or keying.
