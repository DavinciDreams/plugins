---
name: mobile-testing
description: Mobile testing strategies and best practices for the mobile-dev team
---

# Mobile Testing Guidelines

## Mobile Testing Strategies
- Test on real devices when possible
- Use simulators and emulators for initial testing
- Test on multiple iOS and Android versions
- Test on different screen sizes and densities
- Test on different network conditions
- Implement automated testing for critical paths
- Use device farms for comprehensive coverage

## Device Farm Testing
- Use Firebase Test Lab for Android
- Use AWS Device Farm for cross-platform testing
- Use BrowserStack for real device testing
- Test on popular device configurations
- Test on older devices for performance
- Test on different manufacturer devices (Android)
- Test on different iOS device models

## Emulator and Simulator Testing
- Use iOS Simulator for iOS testing
- Use Android Emulator for Android testing
- Test on different API levels
- Test on different screen configurations
- Use emulator features for testing (GPS, camera, etc.)
- Test with different language and region settings
- Test with accessibility features enabled

## UI Testing Frameworks
- **iOS**: XCUITest for UI automation
- **Android**: Espresso for UI testing
- **Cross-Platform**: Appium for cross-platform UI tests
- **React Native**: Detox for React Native testing
- **Flutter**: Flutter integration testing
- Write maintainable UI tests with page object pattern
- Test critical user flows end-to-end

## Performance Testing for Mobile
- Measure app startup time
- Test memory usage and detect leaks
- Monitor battery consumption
- Test network performance and latency
- Test offline behavior and sync
- Use profiling tools (Instruments, Android Profiler)
- Set performance budgets and monitor

## Mobile Accessibility Testing
- Test with VoiceOver (iOS) and TalkBack (Android)
- Test with Dynamic Type (iOS) and font scaling (Android)
- Test with screen magnification
- Verify color contrast ratios
- Test with switch control and other assistive technologies
- Follow WCAG and platform accessibility guidelines
- Test with reduced motion settings

## Beta Testing and Distribution
- **iOS**: Use TestFlight for beta distribution
- **Android**: Use Google Play Internal Testing
- Use Firebase App Distribution for cross-platform
- Collect crash reports and analytics
- Gather user feedback and bug reports
- Test with beta users before public release
- Monitor app store reviews and ratings
