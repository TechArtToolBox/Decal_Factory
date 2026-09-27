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
<img width="242" height="464" alt="image" src="https://github.com/user-attachments/assets/8de97f56-69a0-42fe-9f85-7c1492ebf88f" />

#### Material
The current material for the decal. Changing the material here is identical to changing the material using the material tab in Blender's property panel.
#### EEVEE Alpha
Render/Blend type for the decal material when using EEVEE, and also when in material preview mode in the 3D viewport. This is identical to changing the Render Method of a material in Blender 4.2+, or changing Blend Mode of a material in Blender 4.1 and below. 
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
The distance that a decal is offset from the mesh it affects. The offset field shows the distance from the source mesh. The + and - buttons are used to bring a decal forward or backward. This is also used to change the sort order of decals when they overlap each other. If the change in offset is too small or too large when adjusting with + or -, the offset step can be adjusted in the add-on preferences.  
#### Trim By Angle
Limit decal influence based on angle. When on, the decal will not draw on faces where the face normal vs the decal projection direction create an angle greater than the value set.  
#### Triangulate Decal Mesh
Use triangles for the decal mesh (default). This ensures maximum accuracy when matching the mesh of the source object. There may be edge cases where you prefer a non-triangulated decal mesh, so this option is there for that. If clipping occurs on a non-triangulated decal, increase the offset to compensate. 
#### Copy Source Geo Normals
text
#### Flip Decal UVs
text
#### Force Redraw Decal
text


## Create Decals From Geometry
(placeholder)

## Troubleshooting
(placeholder)
