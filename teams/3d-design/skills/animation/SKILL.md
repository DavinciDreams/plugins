---
name: animation
description: Animation principles, techniques, and best practices for 3D animation
---

# 3D Animation

## Animation Principles

### The 12 Principles of Animation
- **Squash and Stretch**: Convey weight, flexibility, and impact
- **Anticipation**: Prepare audience for upcoming actions
- **Staging**: Present action clearly and unmistakably
- **Straight Ahead vs Pose to Pose**: Different animation workflows
- **Follow-Through and Overlapping Action**: Natural movement flow
- **Slow In and Slow Out**: Natural acceleration and deceleration
- **Arcs**: Natural curved paths of motion
- **Secondary Action**: Reinforce primary action with complementary movements
- **Timing**: Number of frames for action
- **Exaggeration**: Enhance actions for clarity and appeal
- **Solid Drawing**: 3D form and weight
- **Appeal**: Engaging and memorable characters

### Additional Principles
- **Weight**: Convey mass and gravity
- **Balance**: Maintain equilibrium
- **Rhythm**: Create pleasing patterns of movement
- **Personality**: Infuse character into movement
- **Readability**: Ensure actions are clear and understandable

## Keyframe Animation Techniques

### Keyframing Workflow
- **Blocking**: Establish key poses that define the action
- **Breakdowns**: Add intermediate poses to define timing
- **In-Betweening**: Fill in frames between keys
- **Polishing**: Refine curves and add secondary motion
- **Review**: Check animation from multiple angles

### Key Types
- **Pose Keys**: Define the main poses of an action
- **Timing Keys**: Define the timing and spacing
- **Breakdown Keys**: Define the transition between poses
- **In-Between Keys**: Fill in the motion between breakdowns

### Keyframe Spacing
- **Linear**: Constant speed
- **Ease In**: Slow start, accelerates
- **Ease Out**: Fast start, decelerates
- **Ease In Out**: Slow start and end, fast middle
- **Custom**: Custom spacing for specific effects

## Procedural Animation

### Procedural Techniques
- **Physics-Based**: Use physics simulation for realistic movement
- **Inverse Kinematics**: Calculate joint positions from end effector
- **Forward Kinematics**: Calculate end effector from joint positions
- **Constraint-Based**: Use constraints to drive animation
- **Mathematical Functions**: Use sine waves, noise, etc.

### Procedural Applications
- **Cloth Simulation**: Simulate cloth physics
- **Hair Simulation**: Simulate hair movement
- **Particle Systems**: Simulate particles and fluids
- **Crowd Simulation**: Simulate crowd behavior
- **Vegetation**: Simulate plant movement

### Procedural vs Keyframed
- **Procedural**: Dynamic, unpredictable, physics-based
- **Keyframed**: Controlled, predictable, artist-directed
- **Hybrid**: Combine both approaches for best results

## Animation Curves and Graph Editor

### Curve Types
- **Linear**: Straight line between keys
- **Bezier**: Smooth curves with handles
- **Stepped**: Instant transitions
- **Constant**: Hold value until next key

### Curve Editing
- **Tangent Handles**: Control curve shape at keys
- **Tangent Types**: Auto, Clamped, Linear, Stepped, Free
- **Curve Smoothing**: Reduce noise in curves
- **Curve Filtering**: Apply filters to curves
- **Curve Copying**: Copy curves between attributes

### Graph Editor Techniques
- **Offset Keys**: Offset keys for overlapping action
- **Scale Keys**: Scale timing of animation
- **Mirror Keys**: Mirror keys for symmetrical actions
- **Cycle Keys**: Create looping animations
- **Bake Simulation**: Convert procedural animation to keys

## Animation Blending and State Machines

### Animation Blending
- **Blend Shapes**: Blend between facial expressions
- **Blend Trees**: Blend between animations based on parameters
- **Layer Blending**: Blend between animation layers
- **Additive Blending**: Add animation on top of base animation
- **Crossfading**: Smooth transition between animations

### State Machines
- **States**: Individual animations or animation groups
- **Transitions**: Movement between states
- **Conditions**: Rules for when transitions occur
- **Parameters**: Variables that control transitions
- **Blend Trees**: Blend between animations based on parameters

### Animation Layers
- **Base Layer**: Primary animation
- **Additive Layers**: Additive animation on top
- **Override Layers**: Override base animation
- **Masking**: Apply layers to specific body parts
- **Layer Blending**: Control layer influence

## Performance Optimization for Animations

### Optimization Techniques
- **Reduce Key Count**: Remove unnecessary keys
- **Simplify Curves**: Reduce curve complexity
- **Use IK/FK Efficiently**: Don't overuse IK
- **Optimize Blend Trees**: Reduce blend tree complexity
- **Use Animation Compression**: Compress animation data
- **Reduce Bone Count**: Remove unnecessary bones

### Real-Time Considerations
- **Frame Rate**: Maintain target frame rate
- **Memory Usage**: Minimize animation memory
- **CPU Usage**: Reduce animation CPU cost
- **GPU Usage**: Minimize GPU impact
- **Network**: Reduce network bandwidth for multiplayer

### Platform-Specific Optimization
- **Mobile**: Lower bone count, simpler animations
- **Console**: Medium optimization, balance quality and performance
- **PC**: Higher quality, more complex animations
- **VR**: High frame rate priority, reduced complexity
- **AR**: Real-time performance priority

## Animation Export and Integration

### Export Formats
- **FBX**: Most common format, supports animation
- **Maya ASCII/Binary**: Maya native format
- **Blender**: Blender native format
- **Collada (DAE)**: Open standard format
- **glTF/GLB**: Web-ready format

### Export Settings
- **Bake Animation**: Bake all constraints and IK to FK
- **Sample Rate**: Set keyframe sampling rate
- **Animation Compression**: Apply compression to reduce file size
- **Root Motion**: Include or exclude root motion
- **Animation Takes**: Export specific animation takes

### Integration
- **Unity**: Import FBX, create Animator Controller, set up animation clips
- **Unreal**: Import FBX, create Animation Blueprint, set up animation montage
- **Godot**: Import glTF/FBX, create AnimationPlayer, set up animation tree
- **Web**: Use Three.js or Babylon.js with glTF animations
- **Custom**: Parse animation data and apply to custom systems
