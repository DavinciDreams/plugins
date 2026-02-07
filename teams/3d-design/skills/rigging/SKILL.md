---
name: rigging
description: Rigging fundamentals, skeleton setup, and animation controls
---

# Rigging

## Skeleton and Joint Hierarchy

### Joint Placement
- **Anatomical Accuracy**: Place joints following anatomical structure
- **Deformation Considerations**: Position joints for optimal deformation
- **Joint Orientation**: Orient joints for proper rotation axes
- **Joint Hierarchy**: Create logical parent-child relationships
- **Naming Conventions**: Use consistent, descriptive joint names
- **Scale and Proportions**: Maintain proper scale and proportions

### Joint Types
- **Ball Joints**: 3 degrees of freedom (shoulder, hip)
- **Hinge Joints**: 1 degree of freedom (elbow, knee)
- **Universal Joints**: 2 degrees of freedom (wrist, ankle)
- **Root Joint**: Base of the skeleton hierarchy
- **End Joints**: End of joint chains (fingertips, toes)

### Joint Hierarchy
- **Root**: Top of the hierarchy (hips, pelvis)
- **Spine**: Spine joints from pelvis to neck
- **Limbs**: Arms and legs with shoulder/elbow/hand and hip/knee/foot
- **Head**: Head and facial joints
- **Fingers**: Finger joints for detailed hand animation
- **Toes**: Toe joints for detailed foot animation

## IK and FK Controls

### Inverse Kinematics (IK)
- **IK Solvers**: Calculate joint positions from end effector
- **IK Handles**: Controls for IK chains
- **Pole Vectors**: Control IK chain orientation
- **IK/FK Blending**: Switch between IK and FK
- **IK Constraints**: Limit IK movement
- **IK Applications**: Legs, arms, spine, fingers

### Forward Kinematics (FK)
- **FK Controls**: Rotate joints directly
- **FK Chains**: Parent-child joint relationships
- **FK Applications**: Spine, fingers, toes, tail
- **FK Advantages**: Intuitive, predictable, easy to animate
- **FK Disadvantages**: Time-consuming for complex poses

### IK/FK Switching
- **Blend Controls**: Switch between IK and FK
- **Match IK to FK**: Match IK pose to FK pose
- **Match FK to IK**: Match FK pose to IK pose
- **Seamless Transitions**: Smooth switching between modes
- **Animation Considerations**: Plan IK/FK usage in animation

## Facial Rigging and Blendshapes

### Blendshapes
- **Shape Keys**: Create facial expressions
- **Expression Targets**: Create expression targets for blendshapes
- **Phonemes**: Create phoneme targets for lip sync
- **Eye Shapes**: Create eye shape targets
- **Brow Shapes**: Create brow expression targets
- **Mouth Shapes**: Create mouth expression targets

### Facial Rigging Techniques
- **Joint-Based**: Use joints for facial animation
- **Blendshape-Based**: Use blendshapes for facial animation
- **Hybrid**: Combine joints and blendshapes
- **Morph Targets**: Alternative to blendshapes
- **Bone-Driven**: Use bones to drive blendshapes

### Eye Rigging
- **Eye Joints**: Create joints for eye movement
- **Eye Controls**: Create controls for eye direction
- **Eyelid Rigging**: Create controls for eyelid movement
- **Pupil Rigging**: Create controls for pupil dilation
- **Eye Constraints**: Limit eye movement to natural range

## Constraint Systems

### Constraint Types
- **Parent Constraint**: Constrain object to follow parent
- **Orient Constraint**: Constrain object orientation to target
- **Point Constraint**: Constrain object position to target
- **Aim Constraint**: Constrain object to aim at target
- **Scale Constraint**: Constrain object scale to target
- **Geometry Constraint**: Constrain object to follow geometry

### Constraint Applications
- **IK Controls**: Use constraints for IK controls
- **FK Controls**: Use constraints for FK controls
- **Space Switching**: Switch between different spaces
- **Follow Through**: Use constraints for follow-through animation
- **Secondary Motion**: Use constraints for secondary motion

### Constraint Best Practices
- **Constraint Order**: Order constraints for predictable results
- **Constraint Weighting**: Use constraint weights for blending
- **Constraint Limits**: Limit constraint influence
- **Constraint Performance**: Optimize constraints for performance
- **Constraint Cleanup**: Remove unnecessary constraints

## Weight Painting Techniques

### Weight Painting Basics
- **Vertex Groups**: Assign vertices to bone groups
- **Weight Values**: Assign weight values (0-1) to vertices
- **Weight Influence**: Control bone influence on vertices
- **Weight Normalization**: Normalize weights for predictable results
- **Weight Smoothing**: Smooth weights for natural deformation
- **Weight Mirroring**: Mirror weights across symmetry

### Weight Painting Tools
- **Weight Brush**: Paint weights directly on mesh
- **Smooth Brush**: Smooth weights for natural deformation
- **Blur Brush**: Blur weights for smooth transitions
- **Add Brush**: Add weight to vertices
- **Subtract Brush**: Subtract weight from vertices
- **Normalize**: Normalize weights for predictable results

### Weight Painting Best Practices
- **Joint Areas**: Concentrate weight around joints
- **Deformation Paths**: Follow natural deformation paths
- **Weight Distribution**: Distribute weight evenly
- **Weight Limits**: Limit weight to appropriate areas
- **Weight Testing**: Test weights with animation

## Rig Optimization for Real-Time

### Optimization Techniques
- **Reduce Bone Count**: Remove unnecessary bones
- **Simplify Constraints**: Simplify constraint systems
- **Optimize Weights**: Optimize weight painting
- **Use IK/FK Efficiently**: Don't overuse IK
- **Reduce Control Count**: Reduce control complexity
- **Optimize Hierarchy**: Optimize joint hierarchy

### Real-Time Considerations
- **Frame Rate**: Maintain target frame rate
- **Memory Usage**: Minimize rig memory
- **CPU Usage**: Reduce rig CPU cost
- **GPU Usage**: Minimize rig GPU impact
- **Network**: Reduce network bandwidth for multiplayer

### Platform-Specific Optimization
- **Mobile**: Lower bone count, simpler rigs
- **Console**: Medium optimization, balance quality and performance
- **PC**: Higher quality, more complex rigs
- **VR**: High frame rate priority, reduced complexity
- **AR**: Real-time performance priority

## Rig Export and Integration

### Export Formats
- **FBX**: Most common format, supports rigging
- **Maya ASCII/Binary**: Maya native format
- **Blender**: Blender native format
- **Collada (DAE)**: Open standard format
- **glTF/GLB**: Web-ready format

### Export Settings
- **Bake Animation**: Bake all constraints and IK to FK
- **Include Skeleton**: Include skeleton in export
- **Include Blendshapes**: Include blendshapes in export
- **Root Motion**: Include or exclude root motion
- **Animation Takes**: Export specific animation takes

### Integration
- **Unity**: Import FBX, configure Avatar, set up Animator Controller
- **Unreal**: Import FBX, configure Skeleton, set up Animation Blueprint
- **Godot**: Import glTF/FBX, configure Skeleton, set up AnimationPlayer
- **Web**: Use Three.js or Babylon.js with glTF rigging
- **Custom**: Parse rig data and apply to custom systems
