# seabird

A Vim theme based on hue 204 <img src="http://www.colorhexa.com/0099ff.png" height="24" width="24">. The light version is **seagull**; the dark, **petrel**.

seabird is mathematically derived, largely through application of two widely-used [measures](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-contrast.html#visual-audio-contrast-contrast-73-head) of text-on-background readability: the ISO "standard minimum" contrast ratio of 3:1, and the W3C "AA-rated accessible minimum" of 4½:1.

seabird features gui (Linux/Windows GVim, MacVim, Neovim), terminal, and true (24-bit) colour support.

## screenshots

seagull | | petrel
-----------------------------------------------------------------------|------------|---------------
 | |
<img src="http://www.colorhexa.com/0b141a.png" height="24" width="39"> <img src="http://www.colorhexa.com/ff5465.png" height="24" width="39"><br><img src="http://www.colorhexa.com/1d252b.png" height="24" width="39"> <img src="http://www.colorhexa.com/fc6500.png" height="24" width="39"><br><img src="http://www.colorhexa.com/61707a.png" height="24" width="39"> <img src="http://www.colorhexa.com/a69500.png" height="24" width="39"><br><img src="http://www.colorhexa.com/6d767d.png" height="24" width="39"> <img src="http://www.colorhexa.com/11ab00.png" height="24" width="39"><br><img src="http://www.colorhexa.com/787e82.png" height="24" width="39"> <img src="http://www.colorhexa.com/00a695.png" height="24" width="39"><br><img src="http://www.colorhexa.com/85898c.png" height="24" width="39"> <img src="http://www.colorhexa.com/0099ff.png" height="24" width="39"><br><img src="http://www.colorhexa.com/e6eaed.png" height="24" width="39"> <img src="http://www.colorhexa.com/9954ff.png" height="24" width="39"><br><img src="http://www.colorhexa.com/ffffff.png" height="24" width="39"> <img src="http://www.colorhexa.com/ff4db8.png" height="24" width="39"><br><br><img src="img/seagull.jpg" width="100"> | <img src="img/screenshot-seagull-ruby.png" alt="screenshot of seagull, the light seabird theme" width="300"> <img src="img/screenshot-petrel-ruby.png" alt="screenshot of petrel, the dark seabird theme" width="300"> | <img src="http://www.colorhexa.com/0b141a.png" height="24" width="39"> <img src="http://www.colorhexa.com/b8656d.png" height="24" width="39"><br><img src="http://www.colorhexa.com/1d252b.png" height="24" width="39"> <img src="http://www.colorhexa.com/b36b3b.png" height="24" width="39"><br><img src="http://www.colorhexa.com/61707a.png" height="24" width="39"> <img src="http://www.colorhexa.com/8a802d.png" height="24" width="39"><br><img src="http://www.colorhexa.com/6d767d.png" height="24" width="39"> <img src="http://www.colorhexa.com/398f2f.png" height="24" width="39"><br><img src="http://www.colorhexa.com/787e82.png" height="24" width="39"> <img src="http://www.colorhexa.com/2e8c83.png" height="24" width="39"><br><img src="http://www.colorhexa.com/85898c.png" height="24" width="39"> <img src="http://www.colorhexa.com/3b83b3.png" height="24" width="39"><br><img src="http://www.colorhexa.com/e6eaed.png" height="24" width="39"> <img src="http://www.colorhexa.com/8f6cc4.png" height="24" width="39"><br><img src="http://www.colorhexa.com/ffffff.png" height="24" width="39"> <img src="http://www.colorhexa.com/b86195.png" height="24" width="39"><br><br><img src="img/petrel.jpg" width="100">

## installation

### step 1: download the colour scheme

#### option A: manually

Download [`seagull.vim`](https://raw.githubusercontent.com/nightsense/seabird/master/colors/seagull.vim) and/or [`petrel.vim`](https://raw.githubusercontent.com/nightsense/seabird/master/colors/petrel.vim) from this repository and place in directory `~/.vim/colors/` (Linux/Mac) or `%userprofile%\vimfiles\colors\` (Windows).

#### option B: using a plugin manager

For easy management of Vim colour schemes (and other plugins), try a plugin manager. With the [Vundle](https://github.com/VundleVim/Vundle.vim) plugin manager, for instance, just add `Plugin 'nightsense/seabird'` to the list of plugins in your `vimrc`, then run `VundleUpdate`. (To automatically keep plugins up to date with Vundle, add `vim +VundleUpdate +qall` to a startup script or cron job.)

### step 2: activate the colour scheme

Add `colorscheme seagull` or `colorscheme petrel` to your `vimrc`.

Or, if you'd like to switch automatically between them based on time of day, add this block (which activates petrel when launching Vim between 8PM and 8AM, seagull otherwise):

```
if strftime("%H") < 8 || strftime("%H") > 20
colorscheme petrel
else
colorscheme seagull
endif
```

### step 3: configure terminal colours (if using Vim in a terminal)

In order for seagull or petrel to work properly in terminal Vim, the terminal's colours should be set to match those of the active Vim theme.

As of now, this repository only provides one terminal configuration file: `Xresources`, which is used by two popular Linux terminals, xterm and urxvt. If you'd like to see a configuration file for another terminal, feel free to make a [request](https://github.com/nightsense/seabird/issues).

## how seabird took flight

### step 1: choosing a principal hue

Hue 204 <img src="http://www.colorhexa.com/0099ff.png" height="24" width="24"> was chosen because:
- a sky blue colour was desired
- at 100% saturation and value, hue 204 features 3:1 contrast ratio (the ISO readability standard) with a white background

### step 2: choosing base colours

The base colours, which are shared by the light and dark versions of seabird, were selected using the hue/saturation/value model of colour definition.

First, all base colours were assigned hue 204.

Second, saturation levels were assigned. The lightest colour, seagrey8, was assigned 0. For the remaining colours, an excerpt of the Fibonacci sequence was applied.

base colour | role                             | hue ° | saturation %
------------|----------------------------------|-------|-------------
seagrey1    | regular background (petrel)      | 204   | 55
seagrey2    | highlighted background (petrel)  | 204   | 34
seagrey3    | subdued text (petrel)            | 204   | 21
seagrey4    | regular text (seagull)           | 204   | 13
seagrey5    | regular text (petrel)            | 204   | 8
seagrey6    | subdued text (seagull)           | 204   | 5
seagrey7    | highlighted background (seagull) | 204   | 3
seagrey8    | regular background (seagull)     | 204   | 0

Third, value levels were assigned. seagrey8 was set to 100% value. The rest were assigned values based on contrast ratios with other base colours.

this colour was assigned... | ...this value... | ...to meet this contrast ratio\*...         | ...with this colour
----------------------------|------------------|--------------------------------------------|--------------------
seagrey1                    | 10               | 18½:1                                      | seagrey8
seagrey2                    | 17               | 1⅕:1                                       | seagrey1
seagrey3                    | 48               | 3:1                                        | seagrey2
seagrey4                    | 49               | 4½:1                                       | seagrey8
seagrey5                    | 51               | 4½:1                                       | seagrey1
seagrey6                    | 55               | 3:1                                        | seagrey7
seagrey7                    | 93               | 1⅕:1                                       | seagrey8
seagrey8                    | 100              | -                                          | -

- the 18½:1 ratio ensures a 10% value background for the dark theme: a "soft black" good for long-term readability
- the 1⅕:1 ratio provides background highlights that stand out clearly from the regular background
- the 3:1 ratio ensures that subdued text on highlighted background is ISO-compliant
- the 4½:1 ratio ensures that regular text on regular background is AA W3C-compliant

The resulting colours:

seabird base colour                                                             | hex      | hue ° | saturation % | value %
--------------------------------------------------------------------------------|----------|-------|--------------|--------
<img src="http://www.colorhexa.com/0b141a.png" height="24" width="39"> seagrey1 | `0b141a` | 204   | 55           | 10
<img src="http://www.colorhexa.com/1d252b.png" height="24" width="39"> seagrey2 | `1d252b` | 204   | 34           | 17
<img src="http://www.colorhexa.com/61707a.png" height="24" width="39"> seagrey3 | `61707a` | 204   | 21           | 48
<img src="http://www.colorhexa.com/6d767d.png" height="24" width="39"> seagrey4 | `6d767d` | 204   | 13           | 49
<img src="http://www.colorhexa.com/787e82.png" height="24" width="39"> seagrey5 | `787e82` | 204   | 8            | 51
<img src="http://www.colorhexa.com/85898c.png" height="24" width="39"> seagrey6 | `85898c` | 204   | 5            | 55
<img src="http://www.colorhexa.com/e6eaed.png" height="24" width="39"> seagrey7 | `e6eaed` | 204   | 3            | 93
<img src="http://www.colorhexa.com/ffffff.png" height="24" width="39"> seagrey8 | `ffffff` | 204   | 0            | 100

### step 3: choosing seagull accent colours

Accent colour hues were selected from around the (30°-divided) colour wheel: hue 204 plus seven companions.

colour | hue °
-------|------
red    | 354
orange | 24
yellow | 54
green  | 114
teal   | 174
blue   | 204
purple | 264
pink   | 324

To begin with, all hues were set to 100% saturation and value, which might be called the "full blast" form of each hue. Each of these colours has a different 'full blast contrast ratio' (FBCR) with a white background.

colour    | FBCR (white background) | FBCR class
----------|-------------------------|--------------
red       | 4.0                     | high
orange    | 2.9                     | mid
yellow    | 1.3                     | low
green     | 1.4                     | low
teal      | 1.3                     | low
blue      | 3.0                     | mid
purple    | 7.0                     | high
pink      | 3.7                     | high

Each 'FBCR class' was treated as follows:

- mid-contrast hues were left unadjusted
- high-contrast hues were adjusted by lowering saturation by ⅓
- low-contrast hues were adjusted by lowering value by ⅓

Following this, some colours fell just short of ISO compliance (3:1 contrast ratio), and so were tweaked to meet the standard.

seagull accent colour                                                         | hex      | contrast ratio\* | hue ° | saturation % | value %
------------------------------------------------------------------------------|----------|------------------|-------|--------------|--------
<img src="http://www.colorhexa.com/ff5465.png" height="24" width="39"> red    | `ff5465` | 3+               | 354   | 67           | 100
<img src="http://www.colorhexa.com/fc6500.png" height="24" width="39"> orange | `fc6500` | 3                | 24    | 100          | 99
<img src="http://www.colorhexa.com/a69500.png" height="24" width="39"> yellow | `a69500` | 3                | 54    | 100          | 65
<img src="http://www.colorhexa.com/11ab00.png" height="24" width="39"> green  | `11ab00` | 3+               | 114   | 100          | 67
<img src="http://www.colorhexa.com/00a695.png" height="24" width="39"> teal   | `00a695` | 3                | 174   | 100          | 65
<img src="http://www.colorhexa.com/0099ff.png" height="24" width="39"> blue   | `0099ff` | 3                | 204   | 100          | 100
<img src="http://www.colorhexa.com/9954ff.png" height="24" width="39"> purple | `9954ff` | 4+               | 264   | 67           | 100
<img src="http://www.colorhexa.com/ff4db8.png" height="24" width="39"> pink   | `ff4db8` | 3                | 324   | 70           | 100

### step 4: choosing petrel accent colours

The accent colours of the petrel theme were derived from the seagull colours by reducing saturation of all hues by ½, then adjusting value to achieve 4½:1 contrast ratio (AA W3C compliance) with the petrel background.

petrel accent colour                                                          | hex      | contrast ratio\* | hue ° | saturation % | value %
------------------------------------------------------------------------------|----------|------------------|-------|--------------|--------
<img src="http://www.colorhexa.com/b8656d.png" height="24" width="39"> red    | `a86f75` | 4½               | 354   | 34           | 66
<img src="http://www.colorhexa.com/b36b3b.png" height="24" width="39"> orange | `a37252` | 4½               | 24    | 50           | 64
<img src="http://www.colorhexa.com/8a802d.png" height="24" width="39"> yellow | `878044` | 4½               | 54    | 50           | 53
<img src="http://www.colorhexa.com/398f2f.png" height="24" width="39"> green  | `4d8c46` | 4½               | 114   | 50           | 55
<img src="http://www.colorhexa.com/2e8c83.png" height="24" width="39"> teal   | `458a83` | 4½               | 174   | 50           | 54
<img src="http://www.colorhexa.com/3b83b3.png" height="24" width="39"> blue   | `5283a3` | 4½               | 204   | 50           | 64
<img src="http://www.colorhexa.com/8f6cc4.png" height="24" width="39"> purple | `8a72ad` | 4½               | 264   | 34           | 68
<img src="http://www.colorhexa.com/b86195.png" height="24" width="39"> pink   | `a66c8f` | 4½               | 324   | 35           | 65

## notes

The seabird colour scheme files are generated by modifying those of the [flattened](https://github.com/romainl/flattened) colour scheme by Romain Lafourcade, which is in turn derived from the [Solarized](https://github.com/altercation/vim-colors-solarized) colour scheme by Ethan Schnoonover.

Colour adjustment was performed with the [GIMP](https://www.gimp.org/) colour selection tool. Contrast ratios were calculated with [these formulas](https://www.w3.org/TR/WCAG20-TECHS/G18.html#G18-tests).

Photo credits: seagull by [Dan Hurt](https://www.flickr.com/photos/57549136@N02/6031726894), petrel by [Duncan (angrysunbird)](https://www.flickr.com/photos/11056712@N00/5291996898). Both licensed [CC BY-SA 2.0](https://creativecommons.org/licenses/by-sa/2.0/).

\* minimum contrast; actual contrast may be slightly higher (due to discrete jumps in digital colour values)
