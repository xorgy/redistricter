# Introduction #

One of the solvers currently implemented works relatively simply by adjusting district centers and weights and assigning census blocks to the weighted nearest district.


# Details #

Initialization:
  * Assign district centers to random points (block coordinates).
  * Assign census blocks to nearest district center.

Repeat until done:
  * Move district centers towards center of population they were actually assigned.
  * Adjust district weight, nudging weight up or down if there are too few or two many people assigned to it.
  * (optional) Nudge district centers away from underpopulated district centers and towards overpopulated district centers.
  * For each census block, assign census block to the district with the lowest ((distance to block from district center) `*` weight<sub>d</sub>)
  * Fixup district contiguity (because straight-line-nearest can jump across water and other gaps in odd ways)