---
name: unity
description: Unity engine fundamentals and workflows for 3D asset integration
---

# Unity Engine

## Unity Fundamentals

### Project Structure
- **Assets Folder**: Contains all project assets (models, textures, materials, scripts)
- **Scenes**: Individual levels or environments
- **Prefabs**: Reusable game object templates
- **Packages**: External libraries and tools via Unity Package Manager
- **Project Settings**: Global configuration for physics, graphics, input, etc.

### GameObject Hierarchy
- **Transform**: Position, rotation, and scale of objects
- **Parent-Child Relationships**: Object hierarchy for organization and transformation
- **Components**: Modular functionality attached to GameObjects
- **Tags and Layers**: Organization and filtering for game logic

## Unity Scripting and C# Basics

### MonoBehaviour Lifecycle
- **Awake()**: Called when script instance is loaded
- **Start()**: Called before first Update frame
- **Update()**: Called once per frame
- **FixedUpdate()**: Called at fixed time intervals for physics
- **LateUpdate()**: Called after all Update calls complete
- **OnDestroy()**: Called when GameObject is destroyed

### Common Unity APIs
- **Transform**: Access position, rotation, scale
- **Rigidbody**: Physics simulation
- **Collider**: Collision detection
- **Renderer**: Visual rendering control
- **Animation**: Animation playback control
- **Animator**: State machine for animations

## Prefab and Component Architecture

### Prefabs
- **Creating Prefabs**: Drag GameObject to Project window
- **Prefab Variants**: Inherit from base prefab with overrides
- **Nested Prefabs**: Prefabs containing other prefabs
- **Prefab Mode**: Edit prefabs in isolation
- **Prefab Overrides**: Apply or revert changes to prefabs

### Components
- **Mesh Renderer**: Renders 3D meshes
- **Mesh Filter**: Holds mesh data
- **Skinned Mesh Renderer**: Renders animated meshes
- **Animator**: Controls animation playback
- **Rigidbody**: Physics simulation
- **Collider**: Collision detection

## Unity Asset Pipeline and Addressables

### Asset Import
- **Model Import Settings**: Scale, normals, tangents, animation clips
- **Texture Import Settings**: Compression, max size, mipmaps
- **Audio Import Settings**: Compression, load type, format
- **Asset Bundles**: Package assets for runtime loading

### Addressables
- **Addressable Assets**: Load assets by address/label at runtime
- **Asset Groups**: Organize assets by build settings
- **Content Catalog**: Runtime database of addressable assets
- **Asset Loading**: LoadAsync for asynchronous loading
- **Memory Management**: Release and unload assets

## Unity Optimization Techniques

### Rendering Optimization
- **Draw Call Batching**: Combine similar objects into single draw call
- **GPU Instancing**: Render multiple instances with single draw call
- **LOD Groups**: Switch to lower detail models at distance
- **Occlusion Culling**: Skip rendering objects not visible to camera
- **Lightmapping**: Bake lighting for static objects

### Performance Optimization
- **Object Pooling**: Reuse objects instead of instantiating/destroying
- **Script Optimization**: Avoid Update when possible, use coroutines
- **Physics Optimization**: Use fixed timestep, optimize colliders
- **Memory Optimization**: Use object pooling, avoid allocations in Update
- **Profiling**: Use Unity Profiler to identify bottlenecks

## Unity Shader Graph and Visual Effects

### Shader Graph
- **Node-Based Shaders**: Create shaders visually without code
- **PBR Master Node**: Physically based rendering
- **Unlit Master Node**: Non-physically based rendering
- **Custom Properties**: Expose parameters to material inspector
- **Sub-graphs**: Reusable shader logic

### Visual Effects Graph
- **Particle Systems**: Create complex particle effects
- **GPU Particles**: High-performance particle simulation on GPU
- **Event Contexts**: Trigger events based on particle behavior
- **Trails and Ribbons**: Create trail effects
- **Collision Detection**: Particle collision with scene objects

## Unity 3D Asset Integration

### Model Import
- **FBX Import**: Import 3D models from Blender, Maya, etc.
- **Scale Conversion**: Handle different unit systems (cm vs m)
- **Animation Clips**: Extract and configure animation clips
- **Rig Import**: Import humanoid or generic rigs
- **Material Generation**: Auto-generate materials from model

### Material Setup
- **Standard Shader**: PBR-based standard shader
- **Shader Graph Materials**: Custom shader graph materials
- **Material Properties**: Albedo, metallic, smoothness, normal maps
- **Texture Slots**: Assign textures to material properties
- **Material Variants**: Create material variations for different states
