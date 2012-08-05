Cobalt Calibur 3.x
===

Cobalt Calibur 3 is a browser-based MMORPG (or, at least one day, it will be). The backend is written in Node.js and
uses MongoDB for a database engine. The frontend uses the HTML5 Canvas tag to handle drawing of the map, and the map is
resized when the page loads to fit the size of the users screen. It also uses some HTML5 audio for sound effects.

Example Server: http://cobaltcalibur-thomashunter.rhcloud.com/

How To Play
==

Movement is done with the WASD keys. Pressing 1-6 will attempt to build the specified tile. Pressing F will attempt to
harvest / mine / chop / collect the tile in front of the player. As you harvest materials, your inventory in the upper
right will increase. As you place tiles, the inventory will decrease. Unlike other building games (e.g. Minecraft), you
don't keep the items you created in inventory, just the raw materials.

Synthetic Tiles:
==

    1 -> Wooden Wall (4 wood)
    2 -> Wooden Floor (2 wood)
    3 -> Stone Wall (4 stone)
    4 -> Stone Floor (2 stone)
    5 -> Wooden Door (12 wood)
    6 -> Glass Window (4 sand)

Placing synthetic tiles will cause the corruption to be pushed back. Doors will block enemies but will not block players.

Naturally Occuring Tiles
==

    Trees -> Mine to receive 2 wood, becomes stump
    Stump -> Mine to receive 1 wood, becomes grass
    Grass -> Walk on it. Randomly becomes tree
    Dirt -> Walk on it. Randomly becomes grass
    Big Ore -> Mine to receive 2 ore, becomes small ore
    Small Ore -> Mine to receive 1 ore, becomes rubble
    Big Stone -> Mine to receive 2 stone, becomes small stone
    Small Stone -> Mine to receive 1 stone, becomes rubble
    Rubble -> Mine to receive 1 stone, becomes dirt
    Watter -> Mine to receive 1 water, becomes dirt

Every morning, grass can grow a tree, dirt can grow grass. Dirt and grass adjacent to water will become sand. When there
is an earthquake (every few days), it will deposit more stone and ore into the world (and possibly damage buildings).

When the server starts, NPCs can spawn on naturally occuring tiles. They then walk around, never dying.

Game Mechanics
==
Walking in the corruption has a chance of killing the player. Standing adjacent to an enemy will kill the player.
Enemies don't have any AI, they just move. There is no health. There are day and night cycles, but they don't affect
gameplay. There are occasional earthquakes, and they change the landscape.

Emergent Gameplay
==
People eventually start building walls around NPCs. They also build synthetic tiles in patterns to efficiently remove
corrupted areas. They also draw penises and destroy each others houses.

Execute Program
==

    sudo node app.js <PORT=80> <MONGOHOST=127.0.0.1> <MONGOPORT=27017>

I personally run the app using Forever:

    sudo npm install forever -g
    sudo forever start app.js 80 127.0.0.1 27017

Requirements
==

MongoDB, Node.js 0.6+

Screenshot
==

![Cobalt Calibur 3.x Screenshot](https://github.com/tlhunter/Cobalt-Calibur-3/raw/master/resources/screenshot.png)
This is a nighttime screenshot (notice it is dark out). The blob at the top of the screen is a corrupted area.

License
==

Dual BSD/GPL
