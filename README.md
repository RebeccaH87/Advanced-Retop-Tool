# Advanced-Retop-Tool
A more advanced toolset for Blender's Quadriflow retopology tool, designed for cleaner edge detection and UV-ready edge flow.

## Install in Blender

1. Open Blender.
2. Go to `Edit > Preferences > Add-ons`.
3. Click `Install From Disk`.
4. Select the `Retopology-Tool` folder as a .zip archive, or zip the Add-on folder and install that .zip.
5. Make sure `Mesh: Retopology-Tool` is enabled. This should happen by default.
6. Check to see if a new side tab has appeared in your workspace called `Retopology`.
7. If it's there, everything should be working!

## Use

1. Select any mesh object containing ngons.
2. Open the 3D View sidebar with `N`.
3. Open the `Retopology` tab.
4. Click `Preview Ngons` if you want the add-on to select the primary faces it will target if the poly count reduction is disabled.
5. Adjust the Merge Distance and Max Hole Edges to the desired settings, then click `Repair Non-Manifold Only` to prepare the mesh for retopology.
6. Ensure Detect Holes & Circles, Prefer Closed Loops, Fix Spiral Topology, and Adaptive Density are turned on. Set Target Face Count to a number a couple thousand higher than your end target.
7. Click `Retopologize`.
8. Disable Prefer Closed Loops, Fix Spiral Topology, and Adaptive Density. Set the desired target face count.
9. Click `Retopologize` again.
10. Undo and tweak smoothing and feature preservation settings until the desired effect is acheived.

## Notes

- Best results are seen when working from a somewhat clean sculpt.
- Always run `Repair Non-Manifold Geometry` before using the Retopology section of this tool.
- A messy sculpt or model may produce an error. If this occurs, use a voxel remesh modifier, then follow all steps mentioned above.
- If an error still occurs, use a decimate modifier on the model to reduce the initial poly count before following the steps above.
- Leave `Adaptive Density` enabled for the final pass only if tris are desired in the final mesh.
- If this tool removes geometry after running, adjust the `Volume Preserve` and `Surface Projection` settings. Lower smoothing may also reduce this issue. 
- If geometry is still being removed after altering the settings mentioned above, use sculpt mode to increase the thickness of the affected area before running the tool. You can set the cleaned geometry back tot the correct size after the initial opperation.
- `Fix Spiral Topology` only works on narrow, tube-like sections of geometry. It should only be used before the final pass, as it will make the topology very odd, but something the tool can better "understand" for the final pass.
