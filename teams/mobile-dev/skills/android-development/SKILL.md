---
name: android-development
description: Android development guidelines and best practices for the mobile-dev team
---

# Android Development Guidelines

## Kotlin and Jetpack Compose Fundamentals
- Use Kotlin 1.9+ with modern language features
- Prefer Jetpack Compose for new UI components
- Use Compose state management (@State, @Remember, @ViewModel)
- Leverage Kotlin Coroutines for asynchronous operations
- Use Kotlin Flow for reactive streams
- Follow Kotlin coding conventions

## Android Architecture Patterns
- **MVVM**: Use with ViewModel and LiveData/StateFlow
- **Clean Architecture**: Separate data, domain, and presentation layers
- **Repository Pattern**: Abstract data sources
- Implement dependency injection with Hilt
- Separate business logic from UI code
- Use interfaces for abstraction and testing

## Android Jetpack Libraries
- **Room**: Use for local database persistence
- **WorkManager**: Use for background tasks
- **Navigation Component**: Use for app navigation
- **DataStore**: Use for key-value storage
- **Paging 3**: Use for paginated data
- **CameraX**: Use for camera functionality
- **BiometricPrompt**: Use for biometric authentication
- **AppCompat**: Use for backward compatibility

## Material Design 3 Guidelines
- Follow Material Design 3 principles
- Use Material 3 components and theming
- Implement proper elevation and shadows
- Use Material Icons for consistency
- Support different screen sizes and densities
- Implement responsive layouts
- Support Dark Theme properly
- Use motion and animations appropriately

## Android Permissions and Security
- Request runtime permissions properly
- Use permission best practices
- Implement proper certificate pinning
- Use Android Keystore for secure storage
- Follow security best practices
- Implement proper network security configuration
- Use ProGuard/R8 for code obfuscation

## Google Play Store Submission
- Follow Google Play Developer Policies
- Prepare app bundle (AAB) for upload
- Prepare screenshots and store listing
- Test with Internal and Closed Testing tracks
- Handle app updates and versioning properly
- Comply with privacy and data collection policies
- Use Play Console for distribution and analytics

## Android Performance Optimization
- Use Android Profiler for performance analysis
- Optimize APK/AAB size with code shrinking
- Use leak detection tools (LeakCanary)
- Implement proper image loading and caching
- Optimize network requests and data transfer
- Reduce app startup time
- Use efficient layouts and view binding
- Optimize battery usage

## Android Testing Frameworks
- **JUnit**: Use for unit tests
- **Espresso**: Use for UI tests
- **Compose Testing**: Use for Compose UI tests
- **Robolectric**: Use for local unit tests
- **MockK**: Use for mocking in tests
- **Truth**: Use for assertion libraries
- Write testable code with dependency injection
