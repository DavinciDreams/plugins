---
name: cross-platform
description: Cross-platform development guidelines and best practices for the mobile-dev team
---

# Cross-Platform Development Guidelines

## React Native Development
- Use React Native 0.72+ with modern features
- Use functional components with Hooks
- Use TypeScript for type safety
- Implement proper navigation with React Navigation
- Use Redux, MobX, or Zustand for state management
- Follow React Native best practices
- Use Expo for rapid prototyping when appropriate

## Flutter Development
- Use Flutter 3.16+ with Dart 3.0+
- Use StatefulWidget and StatelessWidget appropriately
- Use Provider, Riverpod, or Bloc for state management
- Implement proper navigation with Navigator 2.0
- Follow Flutter best practices and widget composition
- Use Flutter DevTools for debugging
- Leverage pub.dev for packages

## Cross-Platform Architecture Patterns
- **MVVM**: Use with reactive state management
- **BLoC Pattern**: Use with Flutter for business logic
- **Clean Architecture**: Separate layers properly
- **Repository Pattern**: Abstract data sources
- Implement proper dependency injection
- Separate business logic from UI code
- Use shared code for business logic

## Native Module Integration
- Create native modules for platform-specific features
- Use React Native Native Modules for iOS/Android
- Use Flutter Platform Channels for native communication
- Implement proper error handling across platforms
- Maintain consistent APIs across platforms
- Use platform-specific optimizations when needed
- Document native module interfaces

## Cross-Platform State Management
- **React Native**: Redux, MobX, Zustand, Context API
- **Flutter**: Provider, Riverpod, Bloc, GetX
- Implement proper state persistence
- Use immutable state patterns
- Handle async operations properly
- Use middleware for side effects
- Implement proper state hydration

## Cross-Platform Navigation
- **React Native**: React Navigation (Stack, Tab, Drawer)
- **Flutter**: Navigator 2.0, GoRouter, AutoRoute
- Implement deep linking properly
- Handle back button behavior correctly
- Use type-safe navigation when possible
- Implement proper route guards
- Handle navigation state persistence

## Performance Optimization for Cross-Platform Apps
- Use React Native Hermes for JavaScript engine
- Use Flutter's performance best practices
- Implement proper list virtualization
- Optimize image loading and caching
- Use code splitting and lazy loading
- Profile performance with platform tools
- Reduce bundle size with tree shaking
- Use efficient data structures

## Platform-Specific Code Handling
- Use platform-specific file extensions (.ios.tsx, .android.tsx)
- Use conditional platform checks (Platform.OS, Theme.of)
- Implement platform-specific UI components
- Handle platform-specific permissions correctly
- Use platform-specific APIs when needed
- Maintain consistent behavior across platforms
- Document platform-specific differences
