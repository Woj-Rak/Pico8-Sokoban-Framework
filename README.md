# Pico-8 Sokoban Framework
[Try the sample game here!](https://www.lexaloffle.com/bbs/?tid=31703)

The idea of this framework is to allow Pico-8 developers of any skill level to quickly put together their own sokoban games.
Remember to have a look at the "Crate Pusher" cart as an example if you're unclear about something.

## Sprite Flag Mapping
![Sprite Flag Mapping](/img/flag_mapping.png)

## Config Page
The config page is the first tab in the code editor of this cart. This is the only part of the code tab you should have to open if you want to just use the framework as is. The config page consits of variables which allow you  to create a custom start and end menu. All these values have to be set before continuing.

### Variables to set

Crates Setup Section
----------------------
Var name | Description
---------|------------
CRT_COL| When a crate is on top of a "target" tile an outline is rendered around it, this number sets the colour of that outline
PLR_SPR| Number of the sprite to be used as the player sprite.
DEF_CRT_SPR| Number of the default crate sprite
DEF_GRND_SPR| Number of a default ground tile
DEF_TRGT_SPR| Number of the default target sprite

Note: The Default sprite numbers are required to allow for building levels which start with some of the crates already on top of their targets.

Title Screen Section
----------------------
Var name | Description
---------|------------
TITLE_SCREEN.TITLE.TEXT| Title of your game. Rendered on main menu.
TITLE_SCREEN.TITLE_SCREEN.X| Starting x position of the title.
TITLE_SCREEN.TITLE_SCREEN.Y| Starting y position of the title
TITLE_SCREEN.TITLE_SCREEN.COL| Title text colour
TITLE_SCREEN.AUTHOR.TEXT| Your name. Rendered on the main menu.
TITLE_SCREEN.AUTHOR.X| Starting x position of your name.
TITLE_SCREEN.AUTHOR.Y| Starting y position of your name.
TITLE_SCREEN.AUTHOR.COL| Author name text colour
TITLE_SCREEN.INSTRUCTIONS.TXT[n]| For every line of text you would like to print on the instructions section of the main menu add one of these.
TITLE_SCREEN_INSTRUCTIONS.X| Starting x position of the instructions
TITLE_SCREEN_INSTRUCTIONS.Y| Starting y position of the instructions
TITLE_SCREEN_INSTRUCTIONS.LN_SPC| Spacing between the lines of text on the instructions page.
TITLE_SCREEN_INSTRUCTIONS.COL| Instructions text colour.

End Screen Section
----------------------
Var name | Description
---------|------------
END_SCREEN.TXT| Text which will be rendered after the player completes the final level.
END_SCREEN.X| Starting x position of the end text
END_SCREEN.Y| Starting y position of the end text
END_SCREEN.COL| End Text Colour

### LVLS Array
The LVLS array is used to store information about each level so they can be loaded. For every level you create you will need to create a new entry in the LVLS array on the config page.

Here's an example of what an element of LVLS looks like
```
 lvls[1] = {x=0,y=0,soffx=32,soffy=32,widx=8,widy=8,msg="easy start",msg_x=45,msg_y=60}
```
Values
----------------------
Value | Meaning
---------|------------
x | X of the top left corner of your level in the map editor
y | Y of the top left corner of your level in the map editor
soffx | screen offset x - mess with these values to render your level in the middle of the screen
soffy | screen offset y - mess with these values to render your level in the middle of the screen
widx | x width on the 
widy | y height of the level on the map editor (yes I know this should be called height not width)
msg | Text which will be displayed before the player starts the level
msg_x | Starting X position of the pre-level message
msg_y | Starting Y position of the pre-level message

## How to add a new level

### Make Sprites
Make your sprites and set the flags correctly (refer to the flag mapping image at the top of this page)
![](/img/making_sprites.gif)

NOTE: Remember to make sure your crate/ground/target/player sprites are in the positions you have defined at the top of the config page.

### Build the level
Build the level anywhere in the map editor using your sprites.

![](/img/level_making.gif)

### Add the level to the config page
Add the level to the config page.

![](/img/config_level.gif)
### Test the level
![](/img/test_level.gif)

Play your new level!

## Contact Me
If you find any issues or have any suggestions regarding this framework feel free to let me know on my [Twitter](https://twitter.com/wojrakdev) or in the [BBS Thread](https://www.lexaloffle.com/bbs/?tid=31703)
