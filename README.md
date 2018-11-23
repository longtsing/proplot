# ProPlot
A library providing helpful and versatile plotting utilities to hasten the process of crafting publication-quality graphics with `matplotlib`. 

## Showcase

For a showcase of all ProPlot features, check out [**this online jupyter notebook**](https://lukelbd.github.io/proplot).

## Documentation

The full documentation can be found [**here**](https://lukelbd.github.io/proplot). It is a work-in-progress for the time being.

## Overview
Import with
```
import proplot as plot
```
Most of the features below derive from the **`subplots`** command, inspired by the `pyplot` command of the same name. This generates a scaffolding of axes and panels.

Next is the **`format`** method. This method is assigned to every axes generated by `subplots`, and can be used to control the look of your axes with a plethora of keyword arguments.
  
Quick overview of additional features:

  * Geometry: Specify axes aspect ratios without messing up subplot spacing. Panels and inter-axes spaces are held *fixed* in inches, while the figure width or height and individual axes sizes are allowed to change. Border space is trimmed (expanded) without messing with inter-axes spacing. *Incredibly* useful for meeting journal figure-size requirements.'
  * Colors: Provided group of perceptually distinct named colors, powerful colormap-generating tools, ability to trivially swap between "color cycles" and "colormaps". A few new, beautiful colormaps and color cycles are provided. Create colorbars from lists of lines or color strings.
  * Maps: Integration with basemap *and* cartopy. Generate arbitrary grids of map projections in one go. Switch between basemap and cartopy painlessly. Add geographical features as part of the `format` process.

## Installation
This package is a work-in-progress. Currently there is no formal releas on PyPi. However, feel free to install directly from Github using:

```
pip install git+https://github.com/lukelbd/proplot.git#egg=proplot
```

I only push to this repo when new features are completed and working properly.

Dependencies are `matplotlib` and `numpy`. The geographic mapping mapping features require `basemap` or `cartopy`. Note that [basemap is no longer under active development](https://matplotlib.org/basemap/users/intro.html#cartopy-new-management-and-eol-announcement) -- cartopy is integrated more intelligently with the matplotlib API.
<!-- , and therefore has more room for growth. -->
However, for the time being, basemap *retains several advantages* over cartopy (namely [more tools for labeling meridians/parallels](https://github.com/SciTools/cartopy/issues/881) and more available projections -- see [basemap](https://matplotlib.org/basemap/users/mapsetup.html) vs. [cartopy](https://scitools.org.uk/cartopy/docs/v0.15/crs/projections.html)). Therefore, I decided to support both.
<!-- may be preferred in some circumstances. -->

## How is this different from seaborn?
There is already a great matplotlib wrapper called [seaborn](https://seaborn.pydata.org/). What makes this project different?

While some of `proplot`'s tools were inspired by seaborn (in particular much of `colors.py` is drawn from seaborn's `palettes.py`), the goal for this project was quite different -- it is intended to simplify the task of crafting publication-quality graphics, and no more.

Seaborn largely attempts to merge the tasks of data analysis and visualization, and many of its features require neatly tabulated data in a standard form. ProPlot contains no analysis tools -- it is expected that you analyze your data on your own time. Anyway, as an atmospheric scientist, the datasets I use usually do not lend themselves to fitting in a simple DataFrame -- so this seaborn feature was not particularly useful for me. For data analysis tools I use in my physical climatology research, check out my [ClimPy](https://github.com/lukelbd/climpy`) project (still in preliminary stages).

By focusing on this one task, I was able to create a number of powerful features well beyond the scope of `seaborn`. See below for details.

## Donations
This package took a shocking amount of time to write. If you've found it useful, feel free to buy me a cup of coffee :)

[![Donate](https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=5SP6S8RZCYMQA&source=url)
