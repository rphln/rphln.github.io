# Convolutions and Hexagons

## Representation

A map with hexagonal tiles can be represented as a matrix $\theta$: for
a given pair of coordinates $qr$, the matrix element $\theta_{qr}$
represents the contents of the map — obstacles, characters or anything
else — in that position. For convenience reasons, [odd-q offset
coordinates](https://www.redblobgames.com/grids/hexagons/#coordinates-offset)
should work the best.

A tensor $\Theta_{iqr}$, where each channel $i$ is an attribute of the
contents of the tile $\theta_{qr}$, is used as an input to a neural
network. The neighbouring relationships are (more-or-less) maintained,
as seen in [“Map storage in axial
coordinates”](https://www.redblobgames.com/grids/hexagons/#map-storage),
thus convolutional operations should be safe to use.

## Reinforcement learning

Given a [spiral
ring](https://www.redblobgames.com/grids/hexagons/#rings-spiral)
centered at $\phi_{qr}$, one can model the output $R$ of a convolutional
neural network such that…

-   $R_{\alpha+j,q,r}$ represents attacking the $j$th tile in the
    spiral.
-   $R_{\beta+j,q,r}$ represents using a spell against the $j$th tile in
    the spiral.
-   $R_{\gamma+j,q,r}$ represents walking to the $j$th tile in the
    spiral.
