---
name: texturing
description: UV mapping, texture painting, PBR materials, and shader basics
---

# Texturing

## UV Mapping Techniques

### UV Basics
- **UV Coordinates**: 2D coordinates mapping 3D geometry to 2D texture space
- **UV Unwrapping**: Process of flattening 3D geometry into 2D space
- **UV Seams**: Cuts in UV layout to enable flattening
- **UV Islands**: Connected groups of UV faces
- **UV Density**: Consistency of texel density across model
- **UV Space**: 0-1 coordinate space for UV mapping

### UV Unwrapping Methods
- **Automatic Unwrapping**: Algorithmic UV generation
- **Manual Unwrapping**: Manual seam placement and unfolding
- **Projection Mapping**: Project UVs from different views
- **Cylindrical Mapping**: Wrap UVs around cylinder
- **Spherical Mapping**: Wrap UVs around sphere
- **Box Mapping**: Project UVs from 6 directions

### UV Best Practices
- **Minimize Distortion**: Reduce stretching and compression
- **Seam Placement**: Place seams in less visible areas
- **UV Density**: Maintain consistent texel density
- **UV Packing**: Pack UV islands efficiently
- **Multiple UV Sets**: Create additional UV sets for lightmaps, baking
- **UV Organization**: Organize UVs logically for texture painting

## Texture Painting Workflows

### Texture Painting Tools
- **Brush Tools**: Paint, airbrush, smudge, blur
- **Stencils**: Use stencils for precise painting
- **Clone Tool**: Clone texture from one area to another
- **Fill Tool**: Fill areas with color or pattern
- **Masking**: Mask areas to protect from painting
- **Layers**: Use layers for non-destructive painting

### Texture Types
- **Base Color**: Main color of the surface
- **Normal Map**: Surface detail and depth
- **Roughness Map**: Surface roughness for PBR
- **Metallic Map**: Metallic vs non-metallic surfaces
- **Ambient Occlusion (AO)**: Self-shadowing and contact shadows
- **Emission Map**: Emissive/glowing areas
- **Height/Displacement Map**: Actual geometric displacement

### Texture Painting Techniques
- **Hand Painting**: Paint textures by hand
- **Photo Bashing**: Combine photos for textures
- **Procedural Generation**: Generate textures procedurally
- **Baking**: Bake high-poly detail to textures
- **Texture Projection**: Project textures onto model
- **Texture Synthesis**: Generate textures from samples

## PBR (Physically Based Rendering) Materials

### PBR Fundamentals
- **Physically Based**: Based on real-world physics
- **Energy Conservation**: Light energy is conserved
- **Microsurface Theory**: Surfaces have microscopic roughness
- **Fresnel Effect**: Reflectivity varies with viewing angle
- **Metallic Workflow**: Metallic vs non-metallic surfaces
- **Specular Workflow**: Separate specular map

### PBR Texture Maps
- **Albedo/Diffuse**: Base color without lighting
- **Normal**: Surface normal for lighting calculation
- **Roughness**: Surface roughness for specular reflection
- **Metallic**: Metallic vs non-metallic surface
- **Ambient Occlusion**: Self-shadowing and contact shadows
- **Emission**: Emissive/glowing areas

### PBR Material Properties
- **Albedo**: Base color of the surface
- **Roughness**: How rough or smooth the surface is
- **Metallic**: Whether the surface is metallic
- **Normal**: Surface detail and orientation
- **Emission**: Whether the surface emits light
- **Opacity**: Whether the surface is transparent

## Substance Painter and Designer Workflows

### Substance Painter
- **Texture Painting**: Paint textures in 3D space
- **Smart Materials**: Procedural materials with smart masks
- **Layer Stack**: Non-destructive layer system
- **Baking**: Bake high-poly detail to textures
- **Atlas Generation**: Combine multiple textures into single atlas
- **Export**: Export to various formats and engines

### Substance Designer
- **Node-Based**: Create materials with node graph
- **Procedural**: Generate textures procedurally
- **Filters**: Apply filters to textures
- **Gradients**: Create gradients for materials
- **Pattern Generators**: Generate patterns for textures
- **Export**: Export to various formats and engines

### Substance Best Practices
- **Non-Destructive**: Use layers and masks for non-destructive workflow
- **Smart Materials**: Use smart materials for efficiency
- **Baking**: Bake high-poly detail for quality
- **Organization**: Organize layers and materials logically
- **Export Settings**: Configure export settings for target engine
- **Performance**: Optimize textures for performance

## Shader Basics and Node Graphs

### Shader Fundamentals
- **Shaders**: Programs that determine how surfaces are rendered
- **Vertex Shaders**: Process vertices and pass data to fragment shaders
- **Fragment Shaders**: Process fragments (pixels) and determine color
- **Shader Properties**: Exposed parameters for artists
- **Shader Inputs**: Textures, colors, values
- **Shader Outputs**: Final color and other outputs

### Node Graph Shaders
- **Node-Based**: Create shaders visually with nodes
- **Nodes**: Individual operations in shader graph
- **Connections**: Connect nodes to create shader logic
- **Inputs**: Inputs to nodes (textures, colors, values)
- **Outputs**: Outputs from nodes (colors, values)
- **Sub-Graphs**: Reusable shader logic

### Common Shader Nodes
- **Texture Sample**: Sample texture at UV coordinates
- **Math Nodes**: Mathematical operations
- **Color Nodes**: Color operations
- **Vector Nodes**: Vector operations
- **Lerp**: Linear interpolation between values
- **Fresnel**: Fresnel effect based on viewing angle

## Texture Atlasing and Optimization

### Texture Atlasing
- **Atlas Generation**: Combine multiple textures into single atlas
- **UV Packing**: Pack UVs efficiently in atlas
- **Texture Channels**: Pack multiple maps into single texture channels
- **Mipmaps**: Generate mipmaps for distance rendering
- **Texture Arrays**: Use texture arrays for multiple textures

### Texture Optimization
- **Resolution**: Reduce texture resolution where appropriate
- **Format**: Use efficient texture formats (ASTC, ETC2, BC7)
- **Compression**: Apply texture compression
- **Mipmaps**: Generate mipmaps for distance rendering
- **Texture Streaming**: Stream textures based on distance
- **Texture Budget**: Manage texture memory budget

### Platform-Specific Optimization
- **Mobile**: Lower resolution, simpler formats
- **Console**: Medium optimization, balance quality and performance
- **PC**: Higher quality, more complex textures
- **VR**: High frame rate priority, reduced complexity
- **Web**: Efficient formats, progressive loading

## Texture Export and Integration

### Export Formats
- **PNG**: Lossless compression, good for UI and transparency
- **JPG**: Lossy compression, good for photos
- **TGA**: Uncompressed, good for intermediate files
- **PSD**: Photoshop format, good for editing
- **EXR**: High dynamic range, good for baking

### Export Settings
- **Resolution**: Set appropriate resolution
- **Color Space**: Set correct color space (sRGB, Linear)
- **Alpha Channel**: Include or exclude alpha channel
- **Mipmaps**: Generate or exclude mipmaps
- **Compression**: Apply or exclude compression

### Integration
- **Unity**: Import textures, set import settings, assign to materials
- **Unreal**: Import textures, set import settings, assign to materials
- **Godot**: Import textures, set import settings, assign to materials
- **Web**: Use Three.js or Babylon.js with textures
- **Custom**: Parse texture data and apply to custom systems
