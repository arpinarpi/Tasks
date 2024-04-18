# Installation
Installing this addon in `Blender` follows the standard procedure.

Go to **Edit/Preferences/Add-ons**, then click **Install** and fill in the addon **.zip** file path. Employees can find it at **D:\dagor2\tools\dagor3_cdk\pluginBlender**.

After installation, tick the checkbox next to the addon in the list. Before starting work, do some initial setup without closing Preferences:

![1](https://github.com/arpinarpi/Tasks/assets/167418790/8f20ae2a-0a93-4a76-911e-3f22a58c763d)


Manually set the paths for ObjectProperties presets and shader lists to prevent user changes from being unsaved when installing a new addon version. It's recommended to store presets outside the addon folder.

Menu for the presets won't be displayed until the existing directory path is specified.

For employees, it's worth to specify the path to dagorShaders.cfg in the folder with plugins for 3D Max, where it's frequently updated. For outsourcers, there's no need to change the default path, which points to the file in the addon's root folder.

For each project taken to work on, the path to the **\assets\** folder should be specified. Provide a clear name, then click **"ADD Project"** to include it in the available list.

> [!NOTE]
> Many UI elements have a tooltip on hover.

Starting from version dag4blend2.0, additional parameters are included for projects. You can access them in the Projects panel conveniently.

![2](https://github.com/arpinarpi/Tasks/assets/167418790/2961c11e-c664-47a2-a71b-07eaa6e3338d)


Now, after adding a project, you can edit the path directly. This allows for easy resource transfer for example to another disk without needing to delete and re-add the project with a new path.

**Shading mode:** Projects may have slight differences in shader behavior categorized into two main groups - Enlisted-like and Warthunder-like shaders.

**Palettes:** Default global and local palettes are available.

The "Experimental Features" section includes new tools that are functional but may have some limitations.

<img width="396" alt="3" src="https://github.com/arpinarpi/Tasks/assets/167418790/8d6331b8-8ce3-4e45-afa2-5a34d46f644e">


New additions include a composite editor and texture baking tools.

<img width="359" alt="4" src="https://github.com/arpinarpi/Tasks/assets/167418790/e054a23e-fd3f-42fb-95e2-7f586f998526">


You can set the active project and change palettes through the menu in the scene properties, eliminating the need to access User Preferences repeatedly.

> [!IMPORTANT]
> The addon implements the settings when these parameters are changed, but currently only if they exist. Therefore, to correct the shader mode, you must reselect the project after creating at least one dagormat in the scene. Similarly, for palettes, you need to reselect the project after creating a dagormat with painting.
Initially, the global and local palettes will consist of simple red and green fills, and shaders will be in WT mode. To adjust this, simply reselect the project from the dropdown after the first import or asset creation.

# Log and text editors
In this toolkit, text objects are vital, so it is recommended including a text field in the layout, or creating a new window solely for a text field, especially if you're using multiple monitors.


<img width="388" alt="5" src="https://github.com/arpinarpi/Tasks/assets/167418790/68a70044-64bd-4146-a8d3-18480ae4edaf">

The import/export functions (and future functions) record execution details text in the "log". Remember, it doesn't clear automatically, so periodically clear it yourself, ensuring there are no unchecked errors or warnings. To clear it, simply "delete" the text object; the tools will generate a new one when needed. This method might be quicker than selecting and deleting each line individually with backspace/Delete.

For editing object properties(dagormats) of proximates as text, a special text object is also generated - its name is specified in the tooltip.

# Setting up materials
To set up the material for dagor, utilize a dedicated dagormat tab.

<img width="239" alt="6" src="https://github.com/arpinarpi/Tasks/assets/167418790/6813c66e-1d65-43c5-853f-43feea7579d0">


This tab contains multiple sections that can be minimized when not in use.

# Main

<img width="490" alt="7" src="https://github.com/arpinarpi/Tasks/assets/167418790/2c87b5b5-10a8-4f21-a906-8c3094ef2567">

In this section, you can specify whether the material is double-sided and, if so, what type.
**two_sided:** Each triangle is rendered on both sides, resulting in a slightly heavier shader but lighter geometry. This setting is primarily used for dense geometry like tree crowns.
**single_sided:** This option creates a one-sided material where the reverse side is ignored.
**real_two_sided:** Technically still one-sided, but in the engine, each triangle with this material is duplicated and inverted to be visible from the opposite side. While the shader is lighter, it doubles the mesh's weight, so it's preferable for simpler meshes.
Below, there's a list of "legacy" properties: ambient, specular, diffuse, emissive, and power. Hovering over each property provides a tooltip explaining its function.

<img width="467" alt="8" src="https://github.com/arpinarpi/Tasks/assets/167418790/3c766a46-b71f-4b0c-9f68-27d9089ec8b9">

Additionally, this tab allows you to choose a shader from the available options or input a value manually if new shaders have been added to the game but not yet updated in the tools.
The list of shaders and their possible parameters is sourced from **dagorShaders.cfg**, which is typically located at:
**C:\Users<username>\AppData\Roaming\Blender Foundation\Blender<version number>\scripts\addons\dag4blend\**

# Textures

<img width="173" alt="9" src="https://github.com/arpinarpi/Tasks/assets/167418790/8e5a749f-9f1d-444a-a2df-679df0b6a923">

It's straightforward here. This section presents a list of textures being used. Indexes, identical to those stored in dag files, are available in tooltips. You can easily copy and paste paths from AV or Explorer: the quotes will be automatically removed.
# Optional

<img width="232" alt="10" src="https://github.com/arpinarpi/Tasks/assets/167418790/e70ba64b-cbf6-4ac3-8c02-904354badfe7">


Visual editing of shader parameters. You can enter it manually or select from a list, similar to how it works with shader selection.

# Tools

<img width="484" alt="11" src="https://github.com/arpinarpi/Tasks/assets/167418790/0650c8e6-dc8a-408e-99a5-f3306c728d97">


In this section, you can modify the active material in text format. If there's no text editing area, it will be added to the left of the viewport; otherwise, it'll open in the first available text zone.
The search function operates in two modes: exclusively for the active material or for all materials in the scene. You can switch between modes by clicking on the text and indicating the current mode.
For the search function to work correctly, ensure the project is specified accurately. For instance, when working on an asset for Enlisted, specify "Enlisted."

With a single button press, you can locate all textures and proxies (if available in this project). Note that texture search only affects display in the viewport and does not modify the material's path.
The "Rebuild" option reconstructs the material(s) for the viewport, as implied by its name.
After conducting a texture search, it's recommended to use "Update texture paths" to locate and replace non-existent paths with actual ones.

"Clear texture paths" simply removes the directory information, retaining only the texture names.

# Proxy


<img width="236" alt="12" src="https://github.com/arpinarpi/Tasks/assets/167418790/00796b96-98e5-43f6-a396-f053f96a2d52">

As is clear from the above, the addon now includes support for proxymats.

Information regarding proxymats parameters is extracted from the blk file, hence all settings for them remain hidden. Instead, a new tab is being added enabling users to specify the path to the folder containing the proxymats. This path can still be modified either as text or temporarily by unchecking the "is proxymat" checkbox.

Any modifications made can be reverted by reloading the information from the file or, conversely, saved to the proxymat. Moreover, converting any regular material into a proxy is simple—just toggle the checkbox and save it to the preferred folder.

> [!IMPORTANT]
> In Blender, proxymats utilize the filename rather than the user-specified one. During import, the shader is automatically renamed if the names differ.

# Object Properties
Located in the N-panel, in the Dagor tab. Shows the parameters of the active object, so when there are no active objects - it is hidden.

<img width="182" alt="13" src="https://github.com/arpinarpi/Tasks/assets/167418790/0a4e5e35-ac2e-433e-98b2-0257a6270741">


## Properties
Visual editing enables you to add, remove, and adjust parameters individually. The UI format is determined by the value string. If an incorrect UI option is displayed (for instance, prop:r=0 generated an integer switch, the variable requires a fractional part for further configuration), enter the name of the existing parameter and the value in the correct format (e.g., 0.0 instead of 0 for a float slider) in the name field. Specifying the type in the name separated by a colon is essential.

## Presets
Once properties are configured, you can save them as presets and easily apply them to other objects with a few clicks. To save the properties of the active object, specify the name of the future preset and click "Save preset as:". To apply an existing preset, select it from the dropdown and click "Apply preset:". Presets are simple text files, editable in a text editor, so feel free to edit them whenever you need it. Clicking the "open presets folder" button reveals a folder containing all presets in .txt format, where you can add, delete, or edit them. Changes are applied instantly.

## Tools
Editing as text within Blender, similar to editing materials, involves opening a text editor on the file by clicking "Open as text". "Apply..." applies changes from the text, while "Write example" inserts an example into the text (without applying it, as it may require customization for a specific situation). "Transfer Attr" copies a list of properties from the active object and assigns them to all selected ones, saving time compared to manual copying. Since version was 2.1.0 released, the text object "props_temp" opens automatically if the internal text editor is open.

> [!Warning]
> Incorrect values in Object Properties are listed in a separate field labeled "broken properties," separated by ";". This enables manual restoration if needed. Similarly, incorrect values are recorded when utilizing "Apply from text".

# Export
Similar to other import-export addons, the DAG exporter can be accessed through File/Export/. However, for efficiency during multiple re-exports while working, the exporter is also available in the N-menu (is recommended to use). Both options offer identical functionality, so choose the one that suits you best.

## Batch Export
Common parameters:

**vNormals:** Preserves custom normals if applied to an object. Without customization, even with the checkbox active, it exports with anti-aliasing groups.

**applyMods:** Exports geometry with visible modifiers applied, rather than the original form.

**Optimize Materials:** Retains only materials used on at least one polygon for each object.

**Path:** Specifies the destination for saving.

**Cleanup Names:** Ignorance of indexes (.000+) during export.

> [!CAUTION]
> Use "Cleanup..." only for exporting composites for 3D Max! It's risky. There can be bugs. A dag file for a game engine should not contain multiple objects with the same name.

The **Name** field is context-sensitive and appears only when exporting to a single .dag file; in other export modes, it's hidden.
The **Collection** field is also context-sensitive. You are not forced to select a collection from the dropdown by clicking on this field; instead you can simply drag and drop the desired one from the outliner.
Limit by allows you to choose the export mode.






table 

| Mode                   | What will it export? | Input data example | Result Example|
| :---                   |     :---             |        :---:  |:---          |
| Visible                | export all scene contents to Path\ <Name>.dag | <img width="160" alt="14" src="https://github.com/arpinarpi/Tasks/assets/167418790/aa449616-ee6a-4b5f-9b1e-1abf7c746419">  |C:\tmp\asset.dag, Containing all scene objects with custom normals. |
| Sel. Joined            | exporting selected objects to Path\<Name>.dag | <img width="162" alt="15" src="https://github.com/arpinarpi/Tasks/assets/167418790/246241e0-ed2c-4bec-bad4-26d35a1e6711"> |C:\tmp\asset.dag, Containing only the selected scene objects. |
| Sel. Separated         | exporting selected objects to different .dag files. The names of these objects are used as the dag name.            | <img width="294" alt="16" src="https://github.com/arpinarpi/Tasks/assets/167418790/4b5ab762-6d46-434f-846c-2f38649e50b1">|C:\tmp\cube.lod00.dag, C:\tmp\cube.lod01.dag.  |
| Col. Separated         | Saves collections from the hierarchy starting with the selected one, if there are no nested subcollections inside. The 'export Orphans' checkbox allows you to export objects located next to the collections. It will be clearer with an example ->  | <img width="395" alt="17" src="https://github.com/arpinarpi/Tasks/assets/167418790/30338f9a-8c3d-4bad-adb5-93aad253524d">|In the same path (C:\tmp\) cube.lod00.dag will be saved, with visible geometry and occluder inside cube.lod01.dag, with visible geometry and collider inside cube.lod02.dagcube_temp.dag, it will not be exported as the exportOrphans checkbox is not active. If you do not specify the collection at all, then in this case the result will be identical, because the check will start with the SceneCollection, and it contains only the same cube collection    |
| Col. Joined            | Saves the entire contents of the selected collection to a file, named like this collection. Created primarily for viewing asset files created from several files in AV. For example, houses with _dp             |    <img width="396" alt="18" src="https://github.com/arpinarpi/Tasks/assets/167418790/2dd04ade-eafb-4e64-90c3-242fb78d1618">   |C:\tmp\soviet_town_building_5_floors_a_joined.lod00.dag, containing all zero lods related to this building. The collections were linked (transferred in the outliner with Ctrl), i.e. these are not copies, but the same collections. You can prepare the rest of the temporary lodes in the same way. Much faster than selecting objects and entering a name manually. **Please pay attention:** since these are the same collections, and not copies, do not delete them on DEL, but put them away on RMB/Unlink, so as not to overwrite the excess    |


# Collection Properties


<img width="161" alt="19" src="https://github.com/arpinarpi/Tasks/assets/167418790/09b7ef95-b6ae-4541-a4f2-bda9f5804be6">

Just like object properties, it is located in the N-panel. Shows properties of the active collection. Unlike object properties, these properties only exist within Blender and are used for internal purposes.

## Override name
This feature allows you to change the name under which the collection will be exported in **"Col.Separated"** mode. By default, this override is disabled.
When importing .dag files with names longer than 63 characters (blender's limit), the name will be stored in this field to prevent loss of "unfit" characters. However, you can manually reassign it by checking the box and entering a new name:

<img width="311" alt="20" src="https://github.com/arpinarpi/Tasks/assets/167418790/afe6d2e4-f477-45e0-8921-6ea71741d242">

In the example provided, the contents of the collection will be exported to **"C:\tmp\cube.lod00.dag"** instead of **"C:\tmp\Collection.dag"**. However, this isn't the most practical use.
A more useful technique involves specifying a subpath if you need to save several files in different subfolders. This subpath will be appended after the main export path. If you don't need to replace the collection name, simply end the sub-path with the **"*"** symbol. During export, this symbol will be replaced with the collection name:

<img width="334" alt="21" src="https://github.com/arpinarpi/Tasks/assets/167418790/a92f23d6-924c-4a1c-a978-c2d3abf2fa41">

For instance, in this example, the export will occur to **"C:\tmp\subfolder\yet_another_subfolder\cube.lod00.dag"** - a handy approach when dealing with complex assets. For example, with buildings - windows in **"composit_parts\windows*", doors in "composit_parts\doors*"**, etc.

But there's more. If desired, you can completely redefine the path by starting it with an appropriate disk letter:

<img width="236" alt="22" src="https://github.com/arpinarpi/Tasks/assets/167418790/76bbbfe2-f96f-4f6c-9e90-e005f8e5a2d8">

Here the "Path" field will be ignored for this collection, and the file will instead be exported to "D:\EnlistedCDK\develop\assets\rendinst_1lod".

## Type

<img width="182" alt="23" src="https://github.com/arpinarpi/Tasks/assets/167418790/cf5e08f5-2afc-4fa0-b0a9-74b418b0839d">

Utilized by the compositing editor, this field records the type of node during import and is crucial for exact determining the type during export. This helps prevent confusion, particularly with assets that share similar names between compositing and rendering. When creating a composite manually, ensure to specify this field if you plan to export to a composite book.

Although "dynmodel" is included in the list, it's not actively used since dynmodels cannot be organized through composites. The composite importer assumes that all assets with ".lod**.dag" in the name are rendinsts, not dynmodels, for the same reason.

## Geometry Nodes
> [!Important]
> Geometry Nodes cannot currently be used in conjunction with custom normals due to the fact that applying a modifier erases them. When arranging instances of objects using geometry nodes, remember to include the "Realize instances" node. Without this node, the geometry will be lost during export. Technically, up to this node, these instances are similar to "dummy" objects in composite nodes, as they do not have their own geometry.

# Smoothing groups

<img width="390" alt="24" src="https://github.com/arpinarpi/Tasks/assets/167418790/8c48ae0a-fca3-4bd2-8a53-858ea95a1597">


During the development phase, a bug was uncovered in blender's function for calculating smoothing groups when exporting to formats that utilize them. To address this issue, a smoothing group editor has been incorporated. It becomes accessible in Edit Mode when the selection mode is set to Faces.

Upon import, objects retain their smoothing groups from the source file. However, newly created groups lack smoothing, so you must first generate them using the Init button. When smoothing groups are present, the interface operates similarly to 3D Max, but without real-time display. A partial preview is offered under "Convert to Sharp Edges," but it only displays hard points from smoothing groups, not problematic points.

Starting from version 2.1.0, the "Live Update" function has been introduced. When activated, hard points are recalculated automatically when editing smoothing groups. However, this may significantly slow down on heavy geometry, so the option is disabled by default.

In the same version, the feature to select polygons by smoothing group was introduced. Simply click on the button corresponding to the desired group in the "Select by SG" sub-panel.

> [!Note]
> Selection by smoothing group supplements existing selections rather than replacing them. Therefore, if you only intend to select smoothing group 3, for instance, remember to unselect any other groups first.

# When to use?

If there's an area on the model where hard points don't completely separate the surface into enclosed zones, the calculation of smoothing groups may be incorrect and require manual correction. Additionally, smoothing groups may need adjustment after modifying existing dags following import if the groups were saved to an attribute.

<img width="194" alt="25" src="https://github.com/arpinarpi/Tasks/assets/167418790/f9959b93-662a-4b95-895f-fa29b662381e">


The example above illustrates an incorrect calculation. On the right side, there's a single group encompassing everything - the hard edges in the middle will be lost, resulting in shading blurring. Smoothing groups are assigned to each zone delimited by hard edges. However, the specified hard edges will be lost because they don't extend to the opposite side and fail to divide into two separate "islands."

# Import
By analogy with export, there are two methods - standard via File/import and batch via N-panel.

## Import and textures
The .dag file not only stores the texture name but also its path. However, during file transfers, paths often become irrelevant. If the texture specified path doesn't exist or only the name is given in the file, it's replaced with UV-checker. If a texture is used in multiple materials, updating the path in one of them to the correct one will load the texture for the rest.
Texture slots are utilized similar to rendinst_simple, regardless of the selected shader. However, the nodes are organized in a logical pattern rather than overlapping. Images from all slots are now added to the Shader Editor. When Node Wrangler is enabled, they can be viewed by pressing Shift+Ctrl+LMB.

## File/Import

<img width="128" alt="26" src="https://github.com/arpinarpi/Tasks/assets/167418790/4e4a39b2-cfc4-4c0f-9cf1-4b7288fbe589">


File/Import Options:
**Optimize material slots:** Removes unused slots and merges slots with the same material.
**Import LODs:** Allows importing all LODs, not just the selected dag.
**Import dps:** Imports all damage_parts (_dp).
**Import dmgs:** doesn’t need an explanaton😊.
**Replace existing:** Replaces the contents of a collection with the imported asset from the .dag file, rather than creating a duplicate with .001+ in the name, useful for quickly reverting multiple changes.
**Batch import:** Helpful for importing large amounts of data simultaneously.
If you need to import much more dags at a time, batch import becomes handy.

## Batch Import

<img width="210" alt="27" src="https://github.com/arpinarpi/Tasks/assets/167418790/a57f4254-4aa4-43cf-9fca-88a2b10cea6b">


This panel facilitates importing data from a designated folder.

Enabling **"Search in subfolders"** extends the search beyond the specified directory to include all its subfolders for suitable files. Be careful, as Blender may become overwhelmed without proper masks or with big number of matches, attempting to import everything simultaneously.

**"Optimize material slots"** functions similarly to normal import.

**"Masks"** allows setting masks for import similar to searching in .folder.blk. Simplifying input, any set of characters is denoted as "", not ".", and a period is represented simply by a dot, not ".". Masks are separated by ";", and spaces are ignored.

**"Excludes"** follows the same syntax, but for excluding items from imports.

> [!Tip]
> For instance, Masks="asset_a.lod0[0,2]; asset_b_dp"; Excludes="_dmg" imports asset_a.lod00.dag, asset_a.lod02.dag, and all logs of all dp asset_b, excluding their _dmg versions.

**"Path"** indicates the search path.

**"Preserve paths"** retains the full path to the dag (including the file name) in the Collection Property. This is useful for importing files from various folders, making modifications, and then batch exporting each to its designated location.

**"Preserve Smoothing Groups"** stores smoothing groups in an attribute to prevent changes during export. This isn't recommended if you plan to modify the imported geometry, as existing attributes will prevent automatic recalculation from hard edges.

During import, Blender may become unresponsive. To monitor the process, I suggest opening the console (Window/Toggle system console).

# Additional features
There are many cases when you may need to import a single asset currently open in the Asset Viewer or Windows Explorer. Instead of searching for it in File\Import, you can copy the path from AV or Windows Explorer (RMB/copy as path) and paste it into the Path panel of batch import. This automatically transfers the file name to Masks. Clicking on Import will then pull in only the desired asset.

If you only have the asset's name, you can specify it in Masks, then apply the entire project directory as a search path with subfolders using the **"Apply as search path"** button. When the path is unknown, the import may take a couple of seconds longer (search time), but it's often quicker than manually finding the full path.

<img width="280" alt="28" src="https://github.com/arpinarpi/Tasks/assets/167418790/eca287dc-a7f3-4ee7-b8d7-3df23a3614fb">


# Tools

<img width="184" alt="29" src="https://github.com/arpinarpi/Tasks/assets/167418790/2c0f3069-d5fc-4229-ad70-caf2997ceaf8">


The panel continues to undergo enhancements. Tools are organized into blocks to prevent overloading the interface when not in use.

**"Optimize material slots"** consolidates slots with identical materials and eliminates unused ones.

**"Merge Duplicates on selected objects"** combines materials with identical parameters but different indices (e.g., Material and Material.001). Such materials often arise when copying with ctrl+c/ctrl+v since this operation saves the selection to an external blend file and then appends it to the active scene along with all materials.

**"Find missing textures"** searches the selected project folder for textures of all dagormats lacking a valid file path. Similarly, "Find missing proxymats" performs a similar search for proximats.

**"Save textures"** gathers all textures from the selected objects with current paths and saves them to the dag export folder's /textures/ subfolder.

**"Preserve Sharp Edges"** marks hards based on the Autosmooth Angle, adjusting the angle by 180° to match the model in both the scene and the dag. This step isn't necessary before export since it's automatically applied to the exported geometry, leaving the source untouched.

**"Apply Modifiers"** duplicates the exporter option. As the name suggests, it applies modifiers. Similarly, it's unnecessary before export as the exporter preserves the modifiers in the source scene.

**"Clear normals"** removes custom normals from all selected objects.

**"Sort collections recursively"** merges scene collections based on the longest matching name at the beginning. An example of this can be seen in the screenshot for the "Col.Joined" export.

**"Pack orphans"** identifies objects not at the bottom of the hierarchy (already discussed in exporting part) and creates separate collections for them.

**"Setup Destruction"** assigns typical object properties for destruction to all selected objects. 
```
animated_node:b=yes
physObj:b=yes
collidable:b=no
massType:t=none
```
It also creates bboxes with gi_black material, designates them as child objects, and specifies collider parameters.  
```
materialName:t=[значение из поля material]
density:r=[значение из поля density]
massType:t=box
collType:t=box
```

This setup may still require adjustments such as moving and scaling the bboxes to fit the outline better, but it streamlines the setup process.

# Experimental Features. 
## Bake

<img width="383" alt="30" src="https://github.com/arpinarpi/Tasks/assets/167418790/2b709c60-de83-47e9-9c7a-03225f6b0b48">


This panel makes it possible to re-bake textures from heavy shaders to rendinst_simple. Typically used for final builds or porting assets to mobile projects.

The topic is extensive, so it is discussed in a separate article.

## Composite editor.


<img width="185" alt="31" src="https://github.com/arpinarpi/Tasks/assets/167418790/ea7d5b13-22dc-4607-b7a2-76a1fe0555dc">


The name speaks for itself. Also discussed in a separate article.

## General limitations of blender tools:
~~The situation with long names is the same as with composites - more than 63 characters will be cut off, and when trying to import objects of the same name, the index .001 is assigned, which reduces the maximum name length by another 4 characters.~~ 
* Since version 1.2.6, the name is too long and is stored in the Collection Property. 
* Animations are not supported yet


