---
name: blender
description: Blender interface, workflows, and 3D production pipeline
---

# Blender

## Blender Interface and Workflows

### Workspace Layout
- **3D Viewport**: Main viewport for modeling and scene manipulation
- **Outliner**: Hierarchical view of scene objects
- **Properties Panel**: Object, modifier, and material properties
- **Timeline**: Animation timeline and playback controls
- **Graph Editor**: Animation curve editing
- **UV Editor**: UV mapping and texture editing
- **Shader Editor**: Node-based material and shader creation

### Navigation
- **Orbit**: Middle mouse button
- **Pan**: Shift + Middle mouse button
- **Zoom**: Scroll wheel
- **Numpad Views**: 1 (front), 3 (right), 7 (top), 5 (orthographic/perspective)
- **Frame Selected**: Period (.)
- **Frame All**: Home

### Object Modes
- **Object Mode**: Manipulate entire objects
- **Edit Mode**: Edit mesh geometry
- **Sculpt Mode**: Digital sculpting
- **Vertex Paint**: Paint vertex colors
- **Weight Paint**: Paint vertex weights for rigging
- **Texture Paint**: Paint textures directly on model
- **Pose Mode**: Animate rigged characters

## Modeling Tools and Techniques

### Primitives
- **Mesh Primitives**: Cube, Sphere, Cylinder, Cone, Torus, Plane, Monkey
- **Curve Primitives**: Bezier, NURBS curves
- **Surface Primitives**: NURBS surfaces
- **Metaballs**: Organic blobby shapes

### Edit Mode Tools
- **Extrude (E)**: Extrude faces, edges, or vertices
- **Inset (I)**: Create inset faces
- **Bevel (Ctrl+B)**: Bevel edges
- **Loop Cut (Ctrl+R)**: Add edge loops
- **Knife Tool (K)**: Cut custom geometry
- **Bridge Edge Loops**: Connect edge loops
- **Merge (Alt+M)**: Merge vertices
- **Dissolve (X)**: Remove geometry while maintaining shape

### Modifiers
- **Subdivision Surface**: Smooth subdivision
- **Mirror**: Mirror geometry across axis
- **Array**: Duplicate geometry in patterns
- **Boolean**: Combine, subtract, or intersect meshes
- **Decimate**: Reduce polygon count
- **Remesh**: Retopologize mesh
- **Shrinkwrap**: Project mesh onto target surface
- **Solidify**: Add thickness to surfaces

## Sculpting and Retopology

### Sculpt Mode
- **Brushes**: Draw, Clay Strips, Crease, Smooth, Inflate
- **Dyntopo**: Dynamic topology for sculpting
- **Multiresolution**: Subdivision sculpting
- **Masking**: Protect areas from sculpting
- **Falloff**: Control brush influence
- **Stroke Settings**: Spacing, jitter, smoothing

### Retopology
- **Shrinkwrap Modifier**: Project new topology onto sculpt
- **Snap to Face**: Snap vertices to surface
- **Poly Build**: Manual retopology tool
- **Bsurface**: Automatic retopology add-on
- **Quad Remesher**: Automatic quad-based retopology

## Blender Rigging and Weight Painting

### Armature
- **Bone Creation**: Add bones to create skeleton
- **Bone Editing**: Edit bone position, rotation, scale
- **Bone Layers**: Organize bones into layers
- **Bone Groups**: Group bones for organization
- **IK Constraints**: Inverse kinematics setup
- **Bone Collections**: Organize bones in Blender 4.0+

### Rigging Tools
- **Rigify**: Auto-rigging system for characters
- **Auto-Rig Pro**: Commercial rigging add-on
- **Human Meta-Rig**: Humanoid rig template
- **Constraints**: IK, Copy Rotation, Limit Rotation, etc.

### Weight Painting
- **Weight Paint Mode**: Paint vertex weights
- **Brush Settings**: Brush size, strength, falloff
- **Weight Tools**: Normalize, blur, smooth weights
- **Vertex Groups**: Assign vertices to bone groups
- **Mirror Weights**: Mirror weights across symmetry
- **Weight Gradient**: Create smooth weight transitions

## Grease Pencil and Animation Tools

### Grease Pencil
- **2D Drawing**: Draw 2D strokes in 3D space
- **Object Mode**: Manipulate grease pencil objects
- **Edit Mode**: Edit stroke points
- **Draw Mode**: Draw new strokes
- **Sculpt Mode**: Sculpt stroke thickness
- **Vertex Paint**: Paint stroke colors
- **Materials**: Assign materials to strokes

### Animation
- **Keyframing**: Insert keyframes (I)
- **Timeline**: Scrub and playback animation
- **Dope Sheet**: Overview of keyframes
- **Graph Editor**: Fine-tune animation curves
- **NLA Editor**: Non-linear animation editing
- **Action Editor**: Edit animation actions

## Blender to Unity/Unreal Export Pipelines

### Export Settings
- **FBX Export**: File > Export > FBX
- **Scale**: Set to 1.00 for Unity, 0.01 for Unreal
- **Forward Axis**: Set to -Z forward for Unity, -X forward for Unreal
- **Up Axis**: Set to Y up for both engines
- **Apply Transforms**: Apply scale, rotation, location before export
- **Include Selected**: Export only selected objects

### Unity Export
- **Scale**: 1.00 (Unity uses meters)
- **Forward**: -Z forward
- **Up**: Y up
- **Apply Transforms**: Ctrl+A > Apply > Scale, Rotation, Location
- **Export Selected**: Check to export only selected objects

### Unreal Export
- **Scale**: 0.01 (Unreal uses centimeters)
- **Forward**: -X forward
- **Up**: Z up
- **Apply Transforms**: Ctrl+A > Apply > Scale, Rotation, Location
- **Export Selected**: Check to export only selected objects

### Common Export Issues
- **Scale Mismatch**: Ensure correct scale factor for target engine
- **Rotation Issues**: Check forward and up axis settings
- **Material Export**: Materials may need to be recreated in target engine
- **Animation Export**: Ensure animations are baked and exported
- **Texture Paths**: Use relative paths for textures
