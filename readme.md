# distrandomizer 1.0 - Distance, but Randomised (Alpha)

This is a preview/heavily WIP version of an updated form of distrandomizer for Distance 1.0.
The randomizer is somewhat working right now but it is unfinished, untested, and probably has
some bugs. Further experimentation is also planned as I plan to expand the randomizer further
with additional options, to allow for more customization and variety than is possible right now:

- [ ] Expand the randomizer map selection to include more than just Adventure mode for futher variety.
    - [ ] "Open" mode: Maps from all four campaign sets (Adv, LtE, Nexus, Legacy) appear
    - [x] Adventure only
    - [ ] Legacy only
- [ ] Add more options to customize the ability order:
  - [x] All randomized
  - [ ] Start with jets, but wings/jump randomized
  - [x] Fixed ability order (Jump > Flights > Jets)
  - [ ] Campaign+ mode, start with everything
  - [ ] Arcade mode, disable map ability progression and uses whatever the map natively specified.

Note that these plans are subject to change however as I am not sure what I think makes sense to include.

Other planned improvements include updating the randomizer logic to match the Spectrum randomizer mod also made by
me, and add some interactive settings customization on the script to improve the user experience.

## Running the randomzier
First, you need to aquire the randomiser script, and install the
dependencies required to use it:

    $ git clone https://github.com/Tiyenti/distrandomizer-python.git
    $ pip install distanceutils numpy numpy-quaternion
    
After that, you need to get the .bytes files of the original maps, and place them
in the `/maps/adventure/` subdirectory where the script is located. This should be
pre-bundled with the official builds of the randomizer once those are ready.

Once you have the map files, you can run the randomizer script
with Python.

    $ python distrandomiser.py [-s [seed]] [dir_of_level_files]

You can use the `-s` (or `--seed`) command line flag to pass a specific
seed. Otherwise, a random seed will be used. The script will then
take in the map files, edit them, then automatically spit them out
into your MyLevels directory with the filenames `randomiser1` through
`randomiser10`. (Don't worry, all mode tags are stripped so they won't
clog up your my levels list ingame.) A playlist file, `randomiser.xml`,
will also be generated and automatically put into the LevelPlaylists
directory. When you want to play your randomised game, go to the Sprint
mode level select and use the **Randomiser** playlist.
