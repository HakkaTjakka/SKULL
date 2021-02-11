Uploading region files (612) (done)

Request: Please let me know if this level is playable, on what computer / version / setting. I've tried everything, but the bastard loads very slow, and sometimes nothing shows up. I'm converting the bastard now to the Windows 10 Edition (Bedrock), its a c/c++ version of Minecraft. Mojang should learn how to program. Go back to school i would like them to tell. Tia.
![clipboard_small](https://github.com/HakkaTjakka/SKULL/blob/main/Untitled.jpg)

I've addapted the Minecraft World Editor for the aquaworld so you CAN GENERATE IT YOURSELF (See repo).
The same will be done with the BOOM repo with TNT tunnels, and this world, that is based on voxelizing one single 3d object multiple times.
Then you can just start the program, giving some parameters and or with a settings file, AND LARGE SCALE WORLDS ARE GENERATED.
Eventually i want to do that with the BUILD THE EARTH 121 projections. So you can just give gps lat/lon coords, then the program will download 3d data from Google 3d Earth, voxelizes, and converts to BTE 121 projection. So you can voxelize whole cities with one click. For now its a whole manual you have to follow.
If somebody wants to assist or step in, your welcome.

In the end the program will be a multifunctional program to edit and create all sorts of worlds. Vanilla and/or cubic chunks 1.12.2 for now.

The world doesn't look that fantastic, but hey it works. Point is showing how to create (very) large worlds and/or lots of region files, and: That it works.
Lights, glass, coral reef, hills, shore etc doesn't look that great, but you get the idea...
This is where that happens (junkie trash coded...): https://github.com/HakkaTjakka/MinecraftWorldEditor/blob/master/PACMAN_CUBERITE/src/MCEditor/test.cpp#L6039

Voxelizer:
https://github.com/HakkaTjakka/MinecraftWorldEditor/blob/master/PACMAN_CUBERITE/src/viewer/viewer_my_loadobj.h#L2555
https://github.com/HakkaTjakka/MinecraftWorldEditor/blob/master/PACMAN_CUBERITE/src/viewer/viewer_my_loadobj.h#L1867
https://github.com/HakkaTjakka/MinecraftWorldEditor/blob/master/PACMAN_CUBERITE/src/WUPPIE.CPP#L1425
(voxelizer core routines, use these for some product, made it myself!) Thanks for the mathematics on the web. Just like the code i grabbed from github.

The whole world is to heavy for an ordinairy pc, windows, Minecraft, Java etc., but this will be fixed in the future....
Point is to show how to generate enormous worlds from scratch, or based on 2d and/or 3d data.
Program can also be used to scan whole worlds, to give data about it, and/or change things globally, move stuff, extract, insert etc. etc. (To be done...)

***
[![Demo CountPages alpha](https://github.com/HakkaTjakka/SKULL/blob/main/1612398576-p.png)](https://www.youtube.com/watch?v=M2jVaR8xDVY)
(Click to play vid)
***

![clipboard_small](https://github.com/HakkaTjakka/SKULL/blob/main/r.10.24.png)

Update: region files will be deleted, and new upload will start with:
612 region files. Format 1.12.2. Skulls should be (almost) completely be filled up with blocks (solid).
Aim of the game: Show how you can make complete minecraft worlds, from scratch (with c/c++ code), change original (1.12.2 format) region files /worlds, and:
How to use wavefront 3d objects to CONVERT TO VOXELS. A voxel is nothing else then a (discrete) 3d point in space, JUST LIKE MINECRAFT BLOCKS. That is nothing else then a voxel in space that is used as base of a 3d cube. You go from 1 coordinate in space, to 8 (corners of cube), with 6 sides of the cube, and every side will be converted by gpu into two triangles. Going from 1 discrete voxel in space like (x,y,z) = (101,10,1053). Then you go from one 3 dimensional point in space, to 8 corners (8 x 3 values), that eventually leaves you with 6 x 2 = 12 traingles, with 3 corners each = 36 points in space (or shared....), equals 3 x 36 = 108 floating points. (When using a wavefront 3d format with triangles that gets loaded into gpu mem). I'm working on a shader that converts a single voxel into these with a vertex/geometry shader for speed loading / saving of cube worlds. Also some cubes will not show up because they are hidden on 6 sides. And sides don't show up when connected to oether blocks... Etc.
So the program for this thing uses one 3d object. Loads it in wavefront 3d .obj/.mtl/textures format, you can render it realtime, then converts it like you want (size, rotation, position in the world) into voxels. 
Then these voxels are sorted by region files ( width X=512, Z=512), and height 256 (standard minecraft), and also into floors (just like x/z region files) for use with cubic chunks. You can go as heigh and/or low as you want. 
The world includes some things like multiple command command blocks, that (for now) only works if you convert and/or play it with 1.14.4+ or so. The base is 1.12.2 region files (totally different format).
The program can:
Read region files (.mca), based on nbt (named binary tags) storage format (what region files are, like 1024 chunks (16x256x16, columns actually) have their own nbt structure inside the .mca file. The program (Minecraft World Editor) has two systems for that. One for mainly .nbt files (and/or .mca files) for (fast) reading editing and saving, and another one used (MCEditor/GitHub) for reading / editing / writing region files, with all kinds of addons, like mobs, command blocks, etc. Its speeded up for use with whole region files (512 x 256 x 512 blocks) for reading / writing.

-You can convert a Wavefront 3d .obj/.mtl/textures into voxels. (Voxel file, text, will be soon in also .nbt format).
-You can convert a Wavefront 3d into a .nbt file, where only the 3d data is present, that gets loaded into GPU memory (besides the used textures) for speed.
-Soon voxel files will also be in this .nbt format, for highspeed compressed loading/saving on it.
-Voxel files can be converted into Minecraft 1.12.2 region files / schematic files. 
    -Loading a schematic and/or region file in the game takes hours. My program loads a whole region file within one second, creates with code and/or voxels a region file within one second, and saves it within one second, if you don't use expensive code on it. Its meant for bulk creation / conversions. Like whole cities from Google Earth 3d (you can download this data also in Wavefront 3d .obj/.mtl/.texture format), and create whole area's like whole cities like build the earth 1 to 1 scale / projection. Its in the program.
-A region file can be converted into voxels.
-A voxel file can be converted into a Wavefront 3d .obj/.mtl/.textures file. For rendering purposes. In the program is a part that can create normal 3d and/or orthographic projection of 3d wavefront objects (see facebook/youtube/program), creating ENDLESS posters of Google 3d area's downloaded. The same will be used for MINECRAFT WORLDS. The region files will be converted into voxel files, the voxel files into Wavefront 3d format (or other format for rendering), then you can MAKE A POSTER OF YOUR WHOLE WORLD NOT DEPENDING ON THE SIZE OF IT, on a (endless in size) large canvas. 
    -So you can convert a 3d object into voxels. Then convert the voxels into a 3d object (with all cubes as triangles), then convert this again to voxels... (recursive).
Etc. In the end it will be a .nbt reading/editing/writing system. For also reading writing .mca files. Convert it into voxel files. Convert voxel files into region files. Edit/create/write voxel fiels. Create Wavefront 3d into voxels. Voxels into Wavefront, etc. etc. etc. THIS ALL WITH HIGHSPEED C/C++ CODE.
I'm also working on my onw renderer because the program can make large posters and/or video's of the 2d canvas and/or 3d objects etc. The sky is the limit. For now its an experimental prototype machine. In the end you will have a menu and/or command line driven aplication that can do all. BUT FAST! For large scale productions. The code for now is just an example what is possible. 

So the skulls are from one 3d object. Converted into voxels. Giving 612 voxels files sorted by floor (now only one for plain vanilla format, not cubic) and region. Its done with a routine that makes circles of the 3d object.
Then the voxel files are read region by region, and stuff is happening with it. Inside the voxel data for instance on the skulls, is data (also voxels/blocks) that tell if this block is a wall (triangle/face) of the object, or is the block left or right (or both) sides of this triangle, giving you the inside / outside of the object. This is used to fill it up. With formula's you choose the material. You only have the color codes from the textures from the 3d object were you can put in what you want (normals, colors, type).
Then the program adds things like hills, water, and beneath command blocks that act like domino's, in the center of the region files is the start (x/z=512/512) on the bedrock floor. Inside these commandblocks are commands that are performed then, like building coral, placing fish and kelp, putting mobs etc. Whatever you can put into command blocks. Again the sky is the limit. You even can let the command blocks create the whole world that is inside it with commands like setblock/fill etc. (Functions etc.). Problem is different format from different versions. For now you first have to convert or play with 1.14.4 or higher.
Then each voxel file is handled and you got 612 region files.

How it workds exactly? Msg me and i write a manual. The whole system is like controlled garbage, and you need to find your way into it. Its preliminary experimental prototype, and used as example for coders. The code is "junk code", but i'm a code junkie/junkie coder. So that is settled.
Again, its for demonstration, about how large scale worlds you can produce this way. The creation of the voxel files (612) takes like 4 hours. The conversion of these to region files took like 10 hours or so. So within one day you have 12.6 times 12.6 is like 160 SQUARE KILOMETERS of MC 1.12.2

You can create the whole world with it (Minecraft World Editor)

There is code inside it for creating command blocks, mazes, hills, dynamite, and lots more, to create whole worlds from scratch, based on simple computer code.
In the end you are just handeling blocks in a simple north/south/east/west/up/down integer format and block type, so the program will come with an interface so a kid can do it.

That is just my story. Its meant for anybody who comes up with idea's to use the program. Again, everything is inside it, not only the MC stuff, but 3d rendering, gigantic posters, large canvas, downloading / editing 2d maps (like street maps), smooth video recording internal/external ffmpeg player, video editing, vertex/geometry/fragment shaders (can be used as source for creating voxels out of it, or 3d models, etc, hight speed calculus stuff), .nbt handling, VOXELIZER (nowere found on the net so i made it myself), creating / handling millions of voxels/sec., sound, gaming, blitting, sfml, opencv, scripting, its all there in one big executable, created with Codeblocks IDE, the seh 64 mingw (open source) compiler, almost no .dll files, libs, includes, externals, all packed together as one machine. When installed and inited with dirs and .ini file and running, you can code. But there is not a manual for now, only for creating for build the eart 1 to 1 how to handle it, and a few info files. You have to reverse engineer it for yourself, ask me if you dare, or just use simple functions. Its for coders. Not for users (for now). When working alone on a project you have to keep everything in mind. With more people you can do more of course, but also split it up into divisions. Leaving your head only to that. So...
Again: this is only for demonstration and i am waiting for people who come up with ideas on how to use it. For fun.



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
