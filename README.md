# Tactically Programmed Tower Defense (TPTD)

A game where the player directly programs the towers they place.

## Struture

All files located under `tptd`

### `src`

The simulation layer, make updates to this folder for the following purposes:
- Define new tower and enemy types
- Optimizations and enhancements

### `usr`

The player places their solution in here

#### `twr.csv`

Defines the placement of all towers in playthrough format for each row is as follows:

`<type>,<row>,<col>[,<id>]`
- `type`: The type of tower to be placed.  Each available type has a folder in `<repo>/tptd/asset`.
- `row,col`: Location of the tower
- `id` (Optional): A custom ID tag if desired.

#### `__init__.py`

Contains the `twr_func` definition meant to be defined by the player.
- Inputs:
```
coord : 2D-Vector
    Location of the subject tower relative to the home base

tag : str
    An identifier defined by you

LoT : list
    "List of Targets", each entry in this list has the following structure
    - Target Type : str
    - Target Position : 2D-Vector
    - Target Velocity : 2D-Vector

fire : bool
    Indicates whether or not the next round will be fired when chambered

current_dir : angle
    Current bearing of the gun

target_dir : angle
    Target bearing of the gun
```
- Outputs:
```
target_dir
    As defined in `Inputs`

fire
    As defined in `Inputs`

target_dir_is_radians : bool
    Indicates if the output target_dir is in radians
```