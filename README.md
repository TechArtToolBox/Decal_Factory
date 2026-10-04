# Decal Factory
Blender add-on for creating decals

[Quick Start](#quick-startbasics)  
[Adjust Decals](#adjust-decals)  

## Installation
- Download Decal Factory here: (placeholder)  
- Install like any other Blender add-on/extension.  
- The Decal Factory UI can be found in the side panel of the 3D viewport.
- In the Decal Factory panel, check on "Enable Decal Factory".  
  <img width="350" height="306" alt="image" src="https://github.com/user-attachments/assets/c67559ef-f6e8-4a73-8dd0-f46e318ea590" />


## Quick Start/Basics

### Create a Decal
- Click "Add Decal" to enter decal creation mode.
- Left click on any mesh in your scene to create a decal at the click location.  
  <img width="640" height="360" alt="add_decal" src="https://github.com/user-attachments/assets/a830c493-608a-42a8-879c-5d3e8b298dcd" />

### Move/Rotate/Scale and Surface Snapping
- Use Blender's native transform tools to move/rotate/scale the decal. (G/R/S hotkeys, or any of the transform gizmos)
- If a transform is detected, the decal enters "proxy mode". This mode draws an inexpensive preview of your decal as you adjust. The yellow wire cube around the proxy decal shows its area of influence.
- **Snapping:** Hold the control key to snap the decal position and orientation to the surface of other objects when moving.
- To commit your changes press enter, or left click anywhere in the 3D view that isn't the decal. 
    <img width="640" height="360" alt="transform_decal" src="https://github.com/user-attachments/assets/8da490ac-ca0d-4370-98fc-733cce304c54" />


### Change material/texture
- Use Blender's shader editor or the material settings panel to adjust the material on a decal, or assign existing materials from your scene.
- Library materials can also be applied to decals via drag and drop from Blender's Asset Browser window.  
    <img width="640" height="360" alt="library_asset_drag_drop" src="https://github.com/user-attachments/assets/b324c3f9-8d29-41c9-936e-a6867f561955" />

### Duplicate
- Hotkey shift + d to duplicate a decal just like any other object.
  <img width="640" height="360" alt="duplicate_decals" src="https://github.com/user-attachments/assets/41a41123-da5d-41e5-a09c-34bf82cd1b81" />  
  NOTE: if you duplicate a decal, it still shares the same material as the decal it was duplicated from. Make the material unique if you plan on changing it to something different.
  
### Parenting
- Decals can be moved freely to affect any mesh object in the scene.
- Decals are automatically parented to the object they affect.  
  (Auto parenting can be turned off in the add-on preferences)  
  <img width="640" height="360" alt="parenting_decals" src="https://github.com/user-attachments/assets/3667efa3-037b-4e08-91d3-c19e805e1546" />


  
## Adjust Decals
When a single decal is selected, the **Adjust Selected Decal** panel can be used to adjust decal specific settings on a decal.

<img width="243" height="422" alt="image" src="https://github.com/user-attachments/assets/086efb12-8bad-4705-bd45-cf57f2b8336f" />

#### Material  
<img width="236" height="29" alt="image" src="https://github.com/user-attachments/assets/a4822f1b-06bc-4108-afc8-ad59e97fecb5" />  

The current material for the decal. Changing the material here is identical to changing the material using the material tab in Blender's property panel.  

#### Proxy Preview
Choose what type of proxy preview you want when transforming the decal. These are the different types:  
<img width="235" height="163" alt="image" src="https://github.com/user-attachments/assets/59247519-78ff-4b62-a2ec-bad571419700" />
- **Image Auto:** Draw the proxy using the best fit image found from the image nodes in the decal material.
- **Image Custom:** Use this to set a specific image for proxy preview. Helpful if 'Image Auto' is not finding something you like automatically.
- **Color Base:** Use the base color value from the first BSDF node found in the material.
- **Color Emissive:** Use the emissive color value from the first BSDF node found in the material.
- **Color Custom:** Allows you to set a specific color and alpha for the proxy preview.
- **Plane:** Draw the material fully rendered on a flat plane. The advantage here is that the material is lit and shaded like normal meshes, and not a proxy preview. The downside is that it is on a flat plane, and doesn't wrap to the geometry until you apply the decal, which can make precise placement difficult. 
#### Offset  
<img width="238" height="44" alt="image" src="https://github.com/user-attachments/assets/371d500d-d193-4bb1-b66f-42c3fdf0a858" />  

The distance that a decal is offset from the mesh it affects. The offset field shows the distance a decal's vertices are offset from the vertices of the source mesh. The + and - buttons are used to bring a decal closer or further away to the source mesh. This is also used to change the sort order of decals when they overlap each other. If the change in offset is too small or too large when adjusting with + or -, the offset amount can be adjusted in the add-on preferences for Decal Factory under 'Decal Offset Step'.  

#### Trim By Angle  
<img width="241" height="33" alt="image" src="https://github.com/user-attachments/assets/75a09c40-d054-4153-b7a4-278ead8b08b0" />  

Limit decal influence based on angle. When on, the decal will not draw on faces where the face normal vs the decal projection direction create an angle greater than the value set.  
#### Triangulate Decal Mesh  
<img width="234" height="32" alt="image" src="https://github.com/user-attachments/assets/bd87bb44-70d0-4691-9729-73f55555aede" />  

Use triangles for the decal mesh (default). This ensures maximum accuracy when matching the mesh of the source object to prevent clipping/Z fighting. There may be edge cases where a non-triangulated decal mesh is needed, so this option is there for that. If clipping/Z fighting occurs on a non-triangulated decal, increase the offset to compensate. 
#### Copy Source Geo Normals  
<img width="239" height="29" alt="image" src="https://github.com/user-attachments/assets/ae0f53e3-87ec-43c8-9dcc-cb7b9169a82b" />  

Adds a data transfer modifier to the decal that copies the geometry normals from the source mesh. This can help solve issues where a decal is not blending correctly with the underlying geometry.

#### Flip Decal UVs  
<img width="234" height="28" alt="image" src="https://github.com/user-attachments/assets/c8247d7b-9418-422a-9627-9d6486bc4a86" />  

Flip the UVs of a decal in the U or V direction. This can be used to mirror a decal left to right, or top to bottom. NOTE: Flipping the UVs can make the decal look incorrect if it is using parallax in its material.
#### Force Redraw Decal  
<img width="237" height="50" alt="image" src="https://github.com/user-attachments/assets/b8b51362-e7a4-44a3-843c-f200aca1b782" />  

Redraws the mesh of the currently selected decal. Useful if the mesh a decal affects has been changed and the decal needs to update to match, or edge cases where a decal is not drawing correctly, or is stuck in proxy preview mode. 


## Generating New Decals From Existing Geo
The **Generate Decal From Mesh** panel can be used to create new decals based on existing meshes in your scene.  
<img width="235" height="533" alt="image" src="https://github.com/user-attachments/assets/2bb81f01-fcad-4bda-92ee-c4ed4b9bfe18" />  

### Pre Bake Prep
- Model/rotate your source geo so that it faces upward in your scene. The decal will be generated from a top down projection. The location and scale of your source object is not important, the bake will compensate for that automatically.
- Set Blender's render engine to Cycles if it is not already.
### Choosing What Maps To Bake  
<img width="225" height="209" alt="image" src="https://github.com/user-attachments/assets/002e4407-b1ac-40bd-8a88-b5aba3cf7dc7" />  

There are 2 categories of maps that can be baked for your decal, **Standard** and **Advanced**.  
- **Standard Maps:** Color, Normal, Roughness, Metallic, and Emissive.  
  When choosing what standard maps to bake, you only need to bake a map if there is variation in that type across the source mesh. For example, if your source mesh material is a solid color, you DO NOT need to bake color, as the bake will just set the color of the decal to match. The same goes for roughness, metallic, and emissive. For normals, if your mesh is perfectly flat ( simple text for example ) there is no need to bake normals either.
   
- **Advanced Maps:** Height, Ambient Occlusion (AO), and Material IDs.  
  These generate data about the mesh that can then be used in the decal material to generate complex effects.
  More information about how to use these maps can be found here [placeholder]

### Output Settings
<img width="231" height="147" alt="image" src="https://github.com/user-attachments/assets/c42fbb36-d8c3-4312-8823-f4606cacc6bf" />  

#### Output Size
<img width="229" height="37" alt="image" src="https://github.com/user-attachments/assets/400899b9-ea6f-4cde-8a3a-044124545a6d" />  

Choose the output resolution of all baked maps for the newly generated decal. Current options are 256, 512, and 1024. Supersampling can be used to increase bake quality.
#### Use Supersampling
<img width="228" height="30" alt="image" src="https://github.com/user-attachments/assets/d6f7fc1c-ca05-4e74-93c5-00683e8d96db" />  

Supersampling will bake all the maps at double the resolution of the output size and then downsample them to the final output size. The drawback being a longer bake time, but the upside being smoother results. (This image is zoomed in way closer than the camera should ever be to a 512x512 decal, but is useful to see the difference)  
<img width="820" height="303" alt="image" src="https://github.com/user-attachments/assets/e74d6080-d260-46b2-b900-80299cd9818b" />  

#### Output Folder
<img width="229" height="53" alt="image" src="https://github.com/user-attachments/assets/bcbbf5e9-a758-429b-b4a5-e70bd9d33cc1" />  

Where to save the baked images. Use the folder icon to select a folder path, or type it in manually. If the folder does not exist or is not writable, baking will exit early and warn about the path being invalid. 

#### Bake Name
<img width="233" height="36" alt="image" src="https://github.com/user-attachments/assets/0281ab39-526c-4f0b-85c6-73a6450d62d3" />  

This name will be used to name the newly created decal, it's material, and all of the baked images related to the bake. If the name already exists in your scene, it will automatically append '.001', '.002' etc, just like with any other Blender naming clash.  
**IMPORTANT:** If the name does not exist in your scene, but files with the same name and output folder exist, THEY WILL BE OVERWRITTEN. Be mindful of that when choosing bake output.
### Generate Decal From Mesh
Now that all the settings are in place, **perform the actual bake**:  
Select your source mesh, and click the 'Generate Decal From Mesh Button'  
<img width="234" height="33" alt="image" src="https://github.com/user-attachments/assets/e6d8b203-39b5-42cc-b6c6-2dc3ddb3b85b" />  

The Blender UI will freeze during the bake, this is to be expected.  
The bake can take anywhere from 30 seconds to 5+ minutes depending on your bake settings, computer hardware, and Blender version.  
Once the bake is complete, the newly created decal will appear above the source mesh and it will be selected.  
Here is an example of a decal bake result of Suzanne ( the Monkey )  
<img width="603" height="497" alt="image" src="https://github.com/user-attachments/assets/62dcd483-970e-4e3c-acb7-b8298825a64d" />  

Adjust/Transform the newly created decal exactly like any other decal. Here is that new decal applied to a sphere:  
<img width="529" height="474" alt="image" src="https://github.com/user-attachments/assets/8b027c63-f45e-4c48-85ca-6775b2e43abd" />



**Baking Notes**  
- The Blender UI WILL lock up during a bake. Give it time. 
- Recommended: If it is your first time baking a decal, bake a simple low resolution test decal to get an estimate of how long a basic bake will take on your computer. Then slowly add extra maps/settings to the bake to get an idea of how long things should take with your setup. 
- Watch the bottom of the Blender UI for any warnings about your bake settings. It will exit early if it finds any issues. A few examples:
  <img width="344" height="109" alt="image" src="https://github.com/user-attachments/assets/00cd3ead-3a00-42ae-985f-1cc681742638" /><img width="497" height="93" alt="image" src="https://github.com/user-attachments/assets/276e13f4-fcf2-4d58-a70f-68fe7a75c298" />

- Just like a normal render, bake times depend on your computer and your render settings (gpu vs cpu, choosing the correct render device settings in Blender preferences etc)

 
## Troubleshooting
### General
#### Decal Not Drawing
#### Decal Looks Correct In Viewport, But is Clipping/Acting Weird In Render
<img width="831" height="359" alt="image" src="https://github.com/user-attachments/assets/c26092ab-62d2-41f1-8194-d35ac35f7385" />  

This happens when a decal is projected on a mesh that has a subdivision modifier, but the subdivision modifier has different levels of subdivision for the viewport vs the render:  
<img width="328" height="265" alt="image" src="https://github.com/user-attachments/assets/ad654bcc-a35c-4ef8-a3cf-b8f5cf1608c0" />  
  

**How to solve:**
- Make the subdivision levels match for both the viewport and render, and update the decal if needed using 'Force Redraw Decal' or 'Redraw Decals In Selection' from the Decal Factory UI.  
  <img width="282" height="79" alt="image" src="https://github.com/user-attachments/assets/19c0caaf-fbc6-48fd-84f5-bda73d74950b" />



