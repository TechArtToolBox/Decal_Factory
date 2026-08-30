# Decal Factory
Blender add-on for creating decals  

## Installation
- Download Decal Factory here: (placeholder)  
- Install like any other Blender add-on/extension.  
- Once installed, the Decal Factory UI can be found in the side panel of the 3D viewport.
- In the Decal Factory panel, check on "Enable Decal Factory" to initialize the main decal logic.
  <img width="229" height="260" alt="image" src="https://github.com/user-attachments/assets/0c41ccaf-0d17-49af-a5f8-a6fab148e8ab" />

## Quick Start/Basics

### Create a Decal
- Click "Add Decal" to enter decal creation mode.
- Left click on any mesh in your scene to create a decal at the click location.
### Move/Rotate/Scale and Surface Snapping
- Use Blender's native transform tools to transform the decal.
- If any transform is detected, the decal enters "proxy mode". This mode draws an inexpensive preview of your decal as you adjust. The yellow wire cube around the proxy decal shows its area of influence.
- **Snapping:** Hold the control key to snap the decal position and orientation to the surface of other objects when moving.
- To commit your changes press enter, or left click anywhere in the 3D view that isn't the decal. The decal will regenerate its mesh to match the mesh of the object it affects.
### Change material/texture
- Change a decal's material/textures just like any other object in Blender. Use Blender's shader editor or the material settings panel to adjust or assign existing materials to it. You can also drag and drop materials onto a decal from the asset browser window.
### Duplicate
- Use Blender's normal UI or the hotkey control + D to duplicate a selected decal. Transform the decal as needed after duplication.
- IMPORTANT: if you duplicate a decal, it still shares the same material as the decal it was duplicated from. Be sure to make the material unique if you plan on changing it to something different than the source decal. 
## Create Decals From Geometry
(placeholder)

