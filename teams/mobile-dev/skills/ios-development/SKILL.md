---
name: ios-development
description: iOS development guidelines and best practices for the mobile-dev team
---

# iOS Development Guidelines

## Swift and SwiftUI Fundamentals
- Use Swift 5.9+ with modern language features
- Prefer SwiftUI for new UI components
- Use property wrappers (@State, @Binding, @ObservedObject, @StateObject) appropriately
- Leverage async/await for asynchronous operations
- Use Swift concurrency actors for thread-safe code
- Follow Swift API design guidelines

## UIKit and AppKit Patterns
- Maintain compatibility with UIKit where needed
- Use view controllers with proper lifecycle management
- Implement Auto Layout constraints correctly
- Use delegation and notification patterns appropriately
- Handle memory management with ARC best practices
- Use storyboards and XIBs sparingly; prefer programmatic UI

## iOS Architecture Patterns
- **MVVM**: Use for SwiftUI-based applications
- **MVC**: Use for UIKit-based applications
- **Coordinator**: Use for complex navigation flows
- Implement dependency injection for testability
- Separate business logic from UI code
- Use protocols for abstraction and testing

## Core Data and Persistence
- Use Core Data for complex data models
- Consider SwiftData for SwiftUI applications
- Use UserDefaults for simple key-value storage
- Implement proper data migration strategies
- Use background contexts for heavy operations
- Follow Core Data best practices for performance

## iOS Frameworks
- **Combine**: Use for reactive programming
- **SwiftUI**: Use for declarative UI
- **ARKit**: Use for augmented reality features
- **CoreML**: Use for machine learning integration
- **MapKit**: Use for mapping and location
- **CoreLocation**: Use for GPS and location services
- **AVFoundation**: Use for media capture and playback
- **WidgetKit**: Use for home screen widgets

## App Store Submission and Review Guidelines
- Follow App Store Review Guidelines
- Implement proper in-app purchase handling
- Use App Store Connect for distribution
- Prepare screenshots and metadata
- Test on TestFlight before release
- Handle app updates and versioning properly
- Comply with privacy and data collection policies

## iOS Performance Optimization
- Use Instruments for profiling
- Optimize image assets and use asset catalogs
- Implement lazy loading for large lists
- Use caching strategies appropriately
- Optimize network requests and data transfer
- Reduce app launch time
- Manage memory efficiently to avoid crashes

## Human Interface Guidelines
- Follow Apple's Human Interface Guidelines
- Support Dynamic Type for accessibility
- Implement proper color contrast
- Use SF Symbols for icons
- Support VoiceOver for screen readers
- Implement haptic feedback appropriately
- Design for different screen sizes and orientations
- Support Dark Mode properly
