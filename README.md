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
- Use Blender's regular transform tools to transform the decal. (G/R/S hotkeys, or any of the transform gizmos)
- If any transform is detected, the decal enters "proxy mode". This mode draws an inexpensive preview of your decal as you adjust. The yellow wire cube around the proxy decal shows its area of influence.
- **Snapping:** Hold the control key to snap the decal position and orientation to the surface of other objects when moving.
- To commit your changes press enter, or left click anywhere in the 3D view that isn't the decal. 
    <img width="640" height="360" alt="transform_decal" src="https://github.com/user-attachments/assets/8da490ac-ca0d-4370-98fc-733cce304c54" />


### Change material/texture
- Change a decal's material/textures just like any other object in Blender. Use Blender's shader editor or the material settings panel to adjust or assign existing materials.
- Library materials can also be applied to decals via drag and drop from Blender's Asset Browser window.
### Duplicate
- Use Blender's regular hotkeys/UI to duplicate a selected decal just like any other object. Transform the decal as needed after duplication.
  NOTE: instancing a decal instead of duplicating will result in unwanted results. Always use duplicate.
- IMPORTANT: if you duplicate a decal, it still shares the same material as the decal it was duplicated from. Make the material unique if you plan on changing it to something different than the original decal.
### Parenting
- Decals can be moved at any time to affect any object in the scene.
- Decals are automatically parented to the object they affect.  
  (Auto parenting can be turned off in the add-on preferences if needed)

## Adjust Decal Panel
### Placeholder

## Create Decals From Geometry
(placeholder)

## Troubleshooting
(placeholder)
