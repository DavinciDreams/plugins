---
name: asset-optimization
description: Polygon reduction, LOD creation, texture compression, and real-time optimization
---

# Asset Optimization

## Polygon Reduction Techniques

### Decimation
- **Decimation Algorithms**: Reduce polygon count while preserving shape
- **Decimation Tools**: Use decimation modifiers or tools
- **Decimation Ratio**: Set appropriate decimation ratio
- **Silhouette Preservation**: Maintain silhouette and important details
- **Topology Cleanup**: Clean topology after decimation
- **Quality Assessment**: Assess visual quality after decimation

### Retopology
- **Retopology Tools**: Use retopology tools for clean topology
- **Manual Retopology**: Manual retopology for quality control
- **Automatic Retopology**: Automatic retopology for speed
- **Quad-Based Topology**: Maintain quad-based topology
- **Edge Flow**: Maintain proper edge flow for deformation
- **Topology Optimization**: Optimize topology for performance

### Polygon Reduction Best Practices
- **Prioritize Important Areas**: Keep detail in visible areas
- **Reduce in Less Visible Areas**: Reduce polygons in less visible areas
- **Maintain Silhouette**: Preserve silhouette and important shapes
- **Clean Topology**: Maintain clean, optimized topology
- **Test in Engine**: Test optimized assets in target engine
- **Iterative Process**: Iterate and refine as needed

## LOD (Level of Detail) Creation

### LOD Levels
- **LOD0**: Highest detail, closest distance
- **LOD1**: Medium detail, medium distance
- **LOD2**: Low detail, far distance
- **LOD3+:** Very low detail, very far distance
- **LOD Count**: Determine appropriate LOD count based on asset importance
- **LOD Distances**: Set appropriate transition distances

### LOD Creation Techniques
- **Manual LOD Creation**: Manually create LOD levels
- **Automatic LOD Generation**: Automatically generate LOD levels
- **Decimation**: Use decimation for LOD generation
- **Retopology**: Use retopology for LOD generation
- **Material Reduction**: Reduce material complexity for LODs
- **Texture Reduction**: Reduce texture resolution for LODs

### LOD Transitions
- **Transition Distance**: Set appropriate transition distances
- **Smooth Transitions**: Ensure smooth transitions between LODs
- **Dithering**: Use dithering for smoother transitions
- **Hysteresis**: Use hysteresis to prevent flickering
- **Testing**: Test LOD transitions in target engine
- **Performance**: Verify performance improvements

## Texture Compression and Formats

### Texture Formats
- **ASTC**: Adaptive Scalable Texture Compression (mobile)
- **ETC2**: Ericsson Texture Compression (mobile)
- **BC7**: Block Compression 7 (PC, console)
- **BC5**: Block Compression 5 (normal maps)
- **DXT5**: S3 Texture Compression (legacy)
- **PVRTC**: PowerVR Texture Compression (iOS)

### Texture Compression
- **Lossless Compression**: Lossless compression for quality
- **Lossy Compression**: Lossy compression for size
- **Compression Quality**: Set appropriate compression quality
- **Compression Artifacts**: Check for compression artifacts
- **Platform-Specific**: Use platform-specific compression
- **Testing**: Test compressed textures in target engine

### Texture Optimization
- **Resolution Reduction**: Reduce texture resolution where appropriate
- **Texture Atlasing**: Combine multiple textures into single atlas
- **Channel Packing**: Pack multiple maps into single texture channels
- **Mipmap Generation**: Generate mipmaps for distance rendering
- **Texture Streaming**: Stream textures based on distance
- **Texture Budget**: Manage texture memory budget

## Draw Call Optimization

### Draw Call Reduction
- **Mesh Batching**: Combine meshes into single draw call
- **GPU Instancing**: Render multiple instances with single draw call
- **Static Batching**: Batch static objects
- **Dynamic Batching**: Batch dynamic objects
- **Material Merging**: Merge materials to reduce draw calls
- **Texture Atlasing**: Combine textures to reduce draw calls

### Batching Techniques
- **Static Batching**: Batch static objects into single mesh
- **Dynamic Batching**: Batch dynamic objects at runtime
- **GPU Instancing**: Use GPU instancing for repeated objects
- **SRP Batcher**: Use SRP Batcher in Unity
- **Instanced Rendering**: Use instanced rendering in Unreal
- **Custom Batching**: Implement custom batching solutions

### Draw Call Best Practices
- **Minimize Draw Calls**: Reduce draw calls where possible
- **Batch Similar Objects**: Batch objects with same materials
- **Use Instancing**: Use instancing for repeated objects
- **Optimize Materials**: Optimize materials for batching
- **Test Performance**: Test draw call performance in target engine
- **Profile**: Profile draw calls with profiling tools

## Mesh Optimization for Real-Time Rendering

### Mesh Optimization Techniques
- **Vertex Cache Optimization**: Optimize vertex cache for better performance
- **Overdraw Reduction**: Reduce overdraw for better performance
- **Triangle Count**: Reduce triangle count for better performance
- **Vertex Count**: Reduce vertex count for better performance
- **Mesh Simplification**: Simplify mesh for better performance
- **Mesh Compression**: Use mesh compression for better performance

### Real-Time Considerations
- **Vertex Processing**: Minimize vertex processing
- **Fragment Processing**: Minimize fragment processing
- **Memory Bandwidth**: Minimize memory bandwidth usage
- **GPU Utilization**: Optimize GPU utilization
- **CPU Utilization**: Optimize CPU utilization
- **Frame Rate**: Maintain target frame rate

### Platform-Specific Optimization
- **Mobile**: Lower vertex count, simpler meshes
- **Console**: Medium optimization, balance quality and performance
- **PC**: Higher quality, more complex meshes
- **VR**: High frame rate priority, reduced complexity
- **AR**: Real-time performance priority

## Platform-Specific Optimization Guidelines

### Mobile Optimization
- **Polygon Budget**: Keep polygon count low (1K-10K per object)
- **Texture Resolution**: Keep texture resolution low (512x512 to 1024x1024)
- **Draw Calls**: Minimize draw calls (<100 per frame)
- **Material Complexity**: Simplify materials
- **Shader Complexity**: Simplify shaders
- **Performance**: Target 30-60 FPS

### Console Optimization
- **Polygon Budget**: Medium polygon count (10K-50K per object)
- **Texture Resolution**: Medium texture resolution (1024x1024 to 2048x2048)
- **Draw Calls**: Moderate draw calls (<500 per frame)
- **Material Complexity**: Medium material complexity
- **Shader Complexity**: Medium shader complexity
- **Performance**: Target 60 FPS

### PC Optimization
- **Polygon Budget**: Higher polygon count (50K-100K per object)
- **Texture Resolution**: Higher texture resolution (2048x2048 to 4096x4096)
- **Draw Calls**: Higher draw calls (<1000 per frame)
- **Material Complexity**: Higher material complexity
- **Shader Complexity**: Higher shader complexity
- **Performance**: Target 60+ FPS

### VR Optimization
- **Polygon Budget**: Low polygon count for high frame rate
- **Texture Resolution**: Medium texture resolution
- **Draw Calls**: Minimize draw calls for high frame rate
- **Material Complexity**: Simplify materials for high frame rate
- **Shader Complexity**: Simplify shaders for high frame rate
- **Performance**: Target 90+ FPS

### AR Optimization
- **Polygon Budget**: Low polygon count for real-time performance
- **Texture Resolution**: Low texture resolution for real-time performance
- **Draw Calls**: Minimize draw calls for real-time performance
- **Material Complexity**: Simplify materials for real-time performance
- **Shader Complexity**: Simplify shaders for real-time performance
- **Performance**: Target 60+ FPS

## Optimization Tools and Workflows

### Optimization Tools
- **Unity Profiler**: Profile performance in Unity
- **Unreal Insights**: Profile performance in Unreal
- **RenderDoc**: Graphics debugging and profiling
- **NVIDIA Nsight**: NVIDIA graphics profiling tools
- **AMD Radeon GPU Profiler**: AMD graphics profiling tools
- **Custom Tools**: Custom optimization tools

### Optimization Workflow
- **Profile**: Profile performance to identify bottlenecks
- **Analyze**: Analyze profiling data to identify issues
- **Optimize**: Optimize based on profiling data
- **Test**: Test optimizations in target engine
- **Iterate**: Iterate and refine as needed
- **Document**: Document optimizations and trade-offs

### Optimization Best Practices
- **Profile First**: Profile before optimizing
- **Optimize Bottlenecks**: Optimize identified bottlenecks first
- **Test Changes**: Test each optimization individually
- **Measure Impact**: Measure impact of each optimization
- **Iterate**: Iterate and refine as needed
- **Document**: Document optimizations and decisions
