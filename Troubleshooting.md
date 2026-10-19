 
## Troubleshooting
[Back to main readme file](https://github.com/TechArtToolBox/Decal_Factory/blob/main/README.md#decal-factory)
### General
- #### Decal Not Drawing
- #### Decal Looks Correct In The Viewport, But is Clipping In Render
  <img width="831" height="359" alt="image" src="https://github.com/user-attachments/assets/c26092ab-62d2-41f1-8194-d35ac35f7385" />  

  This happens when a decal is projected on a mesh that has a subdivision modifier, but the subdivision modifier has different levels of subdivision for the viewport vs the render:  
  <img width="328" height="265" alt="image" src="https://github.com/user-attachments/assets/ad654bcc-a35c-4ef8-a3cf-b8f5cf1608c0" />  
  

  **Solve:**
  Make the subdivision levels match for both the viewport and render, and update the decal if needed using 'Force Redraw Decal' or 'Redraw Decals In Selection' from the Decal Factory UI.  
  <img width="282" height="79" alt="image" src="https://github.com/user-attachments/assets/19c0caaf-fbc6-48fd-84f5-bda73d74950b" />


