Remake: Solid skulls on the way...

Turns out (especially on 1.14+) chunkloading is very slow. Possible causes: adding block light (only works in 1.12.2) to voxelized data, and/or hollow structures, filled with also blocks from neighbour objects). So working on getting the blocklight out, and filling up objects by determin face side of triangles (inside/outside object).

# SKULL
 Minecraft world 1.12.2

Made with https://github.com/HakkaTjakka/MinecraftWorldEditor in 4 hours 26 minutes (while sleeping)
611 region files
8.17 GB

Automated build from one Wavefront 3d object, converted to voxels, converted to 1.12.2 region files
Command blocks below surface with multiple commands for effects like placing blocks/mobs domino style triggered on
Karnaugh traject

(Adapted/fasten) code from https://github.com/mingl0280/MCEditor for reading / writing .mca files very quickly (one second to load, 3 to recalc/write)
(https://github.com/HakkaTjakka/MinecraftWorldEditor/tree/master/PACMAN_CUBERITE/src/MCEditor)

Using tiny_obj_loader.h for reading Wavefront .obj/.mtl files

Voxelizer: https://github.com/HakkaTjakka/MinecraftWorldEditor/blob/master/PACMAN_CUBERITE/src/WUPPIE.CPP


***
[![Demo CountPages alpha](https://github.com/HakkaTjakka/SKULL/blob/main/voxel%20files.png)](https://www.youtube.com/watch?v=kiX0ziFujrE)
(Click to play vid)
***
[![Demo CountPages alpha](https://github.com/HakkaTjakka/SKULL/blob/main/region%20files.png)](https://www.youtube.com/watch?v=C-qs36UcUCE)
(Click to play vid)
***
