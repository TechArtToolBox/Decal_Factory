# Decal Factory
Blender add-on for creating decals  

## Installation
- Download Decal Factory here: (placeholder)  
- Install like any other Blender add-on/extension.  
- The Decal Factory UI can be found in the side panel of the 3D viewport.
- In the Decal Factory panel, check on "Enable Decal Factory".  
  <img width="229" height="260" alt="image" src="https://github.com/user-attachments/assets/0c41ccaf-0d17-49af-a5f8-a6fab148e8ab" />

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


  
## Adjust Selected Decal Panel
When a single decal is selected, this panel will populate with controls to adjust settings on the selected decal.
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

The distance that a decal is offset from the mesh it affects. The offset field shows the distance a decal's vertices are away from the vertices of the source mesh. The + and - buttons are used to bring a decal closer or further away to the source mesh. This is also used to change the sort order of decals when they overlap each other. If the change in offset is too small or too large when adjusting with + or -, the offset amount can be adjusted in the add-on preferences for Decal Factory under 'Decal Offset Step'.  

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


## Create Decals From Geometry
(placeholder)

## Troubleshooting
(placeholder)
