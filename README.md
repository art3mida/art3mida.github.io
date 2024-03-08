# Personal portfolio

## TODO:
* Instead of just listing models (worst way to showcase models), make a page for each of the *projects*, where you first describe what it is, what was the purpose, then show multiple renders and scenes, and only then show the model itself and allow the user to rotate it, zoom, and look around. Presenting the model well, and in the environment where it's meant to be used is extremely important.
* Come up with a better layout for the whole webpage. Resume does not need to be in the forefront.
* Clean up the code. Consider using components.

## 2024-03-08
* Started expansion of the personal website to include my portfolio
* Added placeholder 3D models using <model-viewer>:
    * https://modelviewer.dev/

### Learnings:
* <model-viewer> can only use glTF/GLB 3D model format:
    * *"<model-viewer> supports and plans to support only glTF/GLB 3D models. It is the Khronos standard known as the JPEG of 3D and the first format to standardize Physically-Based Rendering (PBR), making your models look realistic under any lighting, on any renderer. It is also compact, compressible, and loads rapidly into the GPU."*
    * Source: https://modelviewer.dev/docs/faq.html
* <model-viewer> also supports lazy loading, by adding a **poster** for your model. This makes sure that the model doesn't 'snap into view' when it's loaded.
    * You can quickly make sure that models look good, as well as export a poster using their editor:
        * https://modelviewer.dev/editor/
    * This is also convenient because exporting the poster this way will ensure that it looks the same way as the inital positioning of the model.
* For <model-viewer> to actually work, you need to have your website (or just the singular HTML file) running in a live server. Here's a quick tool you can use in VSCode:
    * https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer
* There is no way to convert .mb (Maya) files without the Maya software. Sucks to suck, me. Additionally, it has no export to GLB directly. The only way I've been able to do it (so far) was to export as FBX from Maya, import into Blender, and then export as GLB.
* Be very careful with your textures/materials. Research what types of textures/materials your goal format supports BEFOREHAND - it is likely that you can't just go about it doing whatever is easiest and expect it to export fully without any issues.
* To export models along with their materials/textures in Blender, make sure that:
    * Your materials are Principal BSD:
        * Sources:
            * https://medium.com/@joelmalone/how-to-fix-missing-materials-and-textures-when-exporting-a-blender-file-to-gltf-3649cbaf87fb
    * Your textures are image textures:
        * Sources:
            * https://blender.stackexchange.com/questions/195606/how-can-i-export-a-model-with-its-textures-applied
            * https://docs.blender.org/manual/en/2.90/addons/import_export/scene_gltf2.html
        * There is a potential workaround that doesn't look like it does exactly what I want it to do, but maybe there's something useful in it:
            * https://www.youtube.com/watch?v=RQyAsi_Jvmc
    * For Maya, there seems to be a way to automatically do this, but even though I've managed to clear all the errors for Doberman, I'm still getting it without any textures when I import into Blender:
        * https://help.autodesk.com/view/MAYAUL/2023/ENU/?guid=GUID-0F504570-CB7A-49D3-A7A2-83438C353A9C