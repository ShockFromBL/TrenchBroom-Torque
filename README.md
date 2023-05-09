# TrenchBroom-Torque

> TrenchBroom is a free (GPLv3+), cross platform level editor for Quake-engine based games. It supports  **Quake**,  **Quake 2**, and  **Hexen 2**  and runs on  **Windows**  (XP and newer),  **Mac OS X**  (10.6 and newer) and  **Linux**. TrenchBroom is easy to use and provides many simple and advanced tools to create complex and interesting levels with ease.

Although this TrenchBroom profile and guide is mainly intended for Blockland, there is no reason why it wouldn't be inherently supported for other Torque games. This is why the profile was called Torque and not Blockland.

## Setup

This guide assumes you already have basic Blockland mapping knowledge. How to setup a `Map_` add-on and so on and so forth is outside the scope of this tutorial.

### Prerequisites

- TrenchBroom v2023.1 or above available [here](https://github.com/TrenchBroom/TrenchBroom/releases).
- `map2dif_plus.exe` available [here](https://bl.kenko.dev/Utilities/map2dif_plus.exe) (_not_ the original `map2dif.exe` from blockland.us, it won't work here).

### Setup

1. Copy the `profile/Torque/` folder to the `games/` directory under TrenchBroom's root directory.
2. Put `map2dif_plus.exe` in an accessible location for later (placing it into its own folder would be advised as that is what you will have to do any way for exporting).
3. Launch TrenchBroom.
4. Click **New map...**
5. Click **Open preferences...**
6. Scroll down to **Torque (experimental)** and update the Game Path to point to the `TrenchBroom-Torque/` folder (i.e. wherever this file you're currently reading is).
7. Click **Apply** and **OK**.
8. Double click **Torque (experimental)** in the game list to start making a Torque map.

## Exporting workflow

### TrenchBroom

When you are ready to export your map, go to **File > Export** and select **Map**.

You will then need to copy the `.map` file and all the textures you used (including the folders themselves if you used a subfolder structure) into a single directory with `map2dif_plus.exe` inside (i.e. next to the `.map` file).

Your folder structure should look something like this:

```
Map_Example/map2dif_plus.exe
Map_Example/example.map
Map_Example/example_textures/grass.png
Map_Example/example_textures/stone.png
```

When you have finished copying what you need, drag and drop the `.map` file over `map2dif_plus.exe` and it should spit out a `.dif` file for you to use in Blockland.

Even if you used a subfolder structure for your textures, the exporter will still normalize the paths to the root folder, so your `.dif` file and your textures will need to be next to each other for Blockland to see them correctly. For example, the finished folder structure (as in, what you would zip up for release) for the example above should look something like this:

```
Map_Example/example.dif
Map_Example/example.mis
Map_Example/example.txt
Map_Example/grass.png
Map_Example/stone.png
Map_Example/description.txt
```

### Torque Constructor

You can also open the `.map` file in Torque Constructor to make further changes to the map and/or export it to `.dif` from there.

## Useful tips for new TrenchBroom users

### I don't see any textures to assign.

You need to enable the relevant Texture Collection underneath the Texture Browser.

Double clicking the one you want in the Available list works, or you can select it and press the `+` symbol.

### How do I assign a texture to a face and not the entire brush?

Hold `Shift`, click the face and now you will be able to set the texture on the face only. Use `Ctrl Shift` to select multiple faces.

### Is there an equivalent to Torque Constructor's UV alignment?

[Not yet](https://github.com/TrenchBroom/TrenchBroom/issues/143). As of time of writing, you can only reset to face aligned, world aligned and/or change the coordinates manually. You can also do this with multiple faces/brushes selected.

### Where are the CSG tools?

The most important ones, **Subtract** and **Hollow**, can be found in the toolbar at the top (**Edit > CSG**)

Subtract is operated in exactly the same manner as Torque Constructor and other similar level designers. Make a brush, move it inside another and then press the menu option or relevant keybind.

Default keybinds:

- CSG Subtract: `Ctrl K`
- CSG Hollow: `Ctrl Shift K`

### How do I place entities such as lights?

You drag and drop them on to the viewport from the Entity Browser, or right click the viewport and use the **Create Point/Brush Entity** dropdowns.