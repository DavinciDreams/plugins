---
name: modeling
description: 3D modeling fundamentals, techniques, and best practices
---

# 3D Modeling

## 3D Modeling Fundamentals

### Geometry Basics
- **Vertices**: Points in 3D space (x, y, z coordinates)
- **Edges**: Lines connecting vertices
- **Faces**: Surfaces formed by edges (triangles, quads, n-gons)
- **Normals**: Direction a face is pointing
- **Topology**: Arrangement and flow of geometry

### Modeling Workflows
- **Box Modeling**: Starting with primitives and refining
- **Sculpting**: Digital sculpting for organic forms
- **NURBS Modeling**: Mathematical curves and surfaces
- **Procedural Modeling**: Algorithmic generation of geometry
- **Photogrammetry**: Creating models from photos

### Coordinate Systems
- **World Space**: Global coordinate system
- **Local Space**: Object's own coordinate system
- **View Space**: Camera-relative coordinates
- **Screen Space**: 2D screen coordinates

## Hard Surface vs Organic Modeling

### Hard Surface Modeling
- **Characteristics**: Man-made objects, sharp edges, precise shapes
- **Techniques**: Boolean operations, bevels, chamfers, inset
- **Tools**: Edge loops, bevel modifier, boolean modifier
- **Applications**: Vehicles, weapons, architecture, props
- **Best Practices**: Maintain quads, avoid n-gons, use supporting edges

### Organic Modeling
- **Characteristics**: Natural forms, flowing shapes, soft edges
- **Techniques**: Sculpting, retopology, edge flow following anatomy
- **Tools**: Sculpt brushes, dynamesh, remesh, smooth
- **Applications**: Characters, creatures, plants, organic environments
- **Best Practices**: Follow anatomical structure, maintain edge flow for deformation

## Subdivision Modeling Techniques

### Subdivision Surfaces
- **Catmull-Clark**: Standard subdivision algorithm
- **Loop Subdivision**: Alternative subdivision method
- **Smooth Shading**: Smooths surface normals
- **Creases**: Sharp edges on subdivision surfaces
- **Edge Weighting**: Control subdivision strength per edge

### Edge Flow
- **Edge Loops**: Continuous rings of edges
- **Supporting Edges**: Edges that define shape and prevent pinching
- **Poles**: Vertices with 3, 5, or more edges
- **Pole Placement**: Strategic placement for deformation
- **Topology Flow**: Following natural forms and deformation paths

### Subdivision Best Practices
- **Quad-Based Topology**: Maintain primarily quads
- **Even Edge Distribution**: Avoid dense and sparse areas
- **Avoid N-Gons**: Triangles and quads only
- **Pole Management**: Place poles strategically
- **Edge Weighting**: Use edge creases for sharp edges

## Sculpting Workflows

### Digital Sculpting
- **Primary Forms**: Establish overall shape and silhouette
- **Secondary Forms**: Add major details and features
- **Tertiary Forms**: Add fine details and surface texture
- **Dynamesh**: Dynamic topology for sculpting freedom
- **Remesh**: Retopologize sculpt for cleaner topology

### Sculpting Tools
- **Standard Brush**: Basic sculpting and smoothing
- **Clay Strips**: Build up form with clay-like strokes
- **Crease**: Define sharp edges and wrinkles
- **Smooth**: Blend and soften details
- **Inflate**: Expand geometry outward
- **Pinch**: Pull geometry together
- **Flatten**: Level out geometry

### Sculpting Best Practices
- **Work from Large to Small**: Start with big shapes, add details later
- **Use Reference**: Keep reference images visible
- **Maintain Symmetry**: Use symmetry for bilateral forms
- **Check Silhouette**: View from multiple angles
- **Test Deformation**: Consider how model will deform

## Topology Best Practices

### Clean Topology
- **Quad-Based**: Use primarily quads for predictable deformation
- **Even Distribution**: Maintain consistent edge density
- **Edge Flow**: Follow natural forms and deformation paths
- **Avoid N-Gons**: Use triangles and quads only
- **Pole Placement**: Place poles strategically, not on deformation areas

### Edge Flow for Animation
- **Joint Areas**: Concentrate edge loops around joints
- **Deformation Paths**: Edge flow follows muscle and bone structure
- **Facial Topology**: Edge flow follows facial muscles
- **Bending Areas**: Extra geometry where bending occurs
- **Non-Deforming Areas**: Lower poly count where no deformation needed

### UV-Friendly Topology
- **Minimize Distortion**: Create topology that unwraps cleanly
- **Seam Placement**: Place seams in less visible areas
- **UV Density**: Maintain consistent texel density
- **UV Islands**: Organize UV islands for efficient packing
- **Multiple UV Sets**: Create additional UV sets for lightmaps, baking

## Modeling for Real-Time vs Pre-Rendered

### Real-Time Modeling (Games, VR, AR)
- **Polygon Budget**: Limited by hardware performance
- **LOD Levels**: Multiple detail levels for distance scaling
- **Texture Atlasing**: Combine textures to reduce draw calls
- **Optimized Topology**: Clean, efficient geometry
- **Material Efficiency**: Minimize material count and complexity
- **Platform Constraints**: Mobile, console, PC requirements

### Pre-Rendered Modeling (Film, Animation)
- **High Detail**: Unlimited polygon count within reason
- **Displacement Maps**: Use displacement for fine detail
- **Subdivision**: High subdivision levels for smooth surfaces
- **Complex Materials**: Multiple material layers and passes
- **Render Farm**: Distributed rendering for complex scenes
- **Quality Priority**: Visual quality over performance

### Hybrid Approaches
- **Normal Maps**: Bake high-detail geometry into normal maps
- **Displacement Maps**: Use displacement for large-scale detail
- **Curvature Maps**: Capture surface curvature for materials
- **AO Maps**: Bake ambient occlusion for depth
- **Baking**: Transfer detail from high-poly to low-poly models

## Common Modeling Mistakes

### Topology Issues
- **N-Gons**: Faces with more than 4 edges
- **Non-Manifold Geometry**: Edges with more than 2 faces
- **Floating Vertices**: Vertices not connected to any faces
- **Duplicate Geometry**: Overlapping vertices and faces
- **Inverted Normals**: Faces pointing in wrong direction

### Scale and Proportion
- **Inconsistent Scale**: Objects at different scales
- **Wrong Units**: Modeling in wrong unit system
- **Proportion Errors**: Incorrect relative proportions
- **Scale Issues on Export**: Scale mismatch on export

### UV Issues
- **Distorted UVs**: Stretched or compressed UVs
- **Seams in Visible Areas**: Seams placed on prominent surfaces
- **Overlapping UVs**: UVs occupying same space
- **Inefficient Packing**: Poor UV space utilization
- **Missing UVs**: Objects without UV maps
