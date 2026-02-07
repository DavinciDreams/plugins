# mobile-dev

Mobile development team for iOS, Android, and cross-platform applications with specialist agents that collaborate through phased workflows.

## Team Members

| Agent | Role | Model | Phase | Color |
|-------|------|-------|-------|-------|
| mobile-analyst | Mobile Requirements Analyst | sonnet | discovery | yellow |
| ios-developer | iOS Developer (Swift/SwiftUI) | sonnet | execution | green |
| android-developer | Android Developer (Kotlin/Compose) | sonnet | execution | cyan |
| cross-platform-dev | Cross-Platform Developer (React Native/Flutter) | sonnet | execution | magenta |
| mobile-qa | Mobile QA Engineer | sonnet | review | red |

## Usage

```
/mobile-dev:mobile Build a mobile app with user authentication
```

Check team status:

```
/mobile-dev:status
```

## Workflow

### Feature Development (5 phases)

1. **Discovery** - Mobile analyst analyzes requirements, platform needs, and existing codebase
2. **Planning** - Design approach, ask clarifying questions, get user approval
3. **Execution** - iOS, Android, or cross-platform developers build the feature
4. **Review** - Mobile QA engineer reviews for bugs, performance, accessibility, and platform compliance
5. **Summary** - Document all changes and suggest next steps

### Bug Fix (3 phases)

1. **Discovery** - Understand the bug across platforms
2. **Execution** - Fix and test
3. **Review** - QA validates the fix

### Release (5 phases)

1. **Discovery** - Analyze release requirements and platform changes
2. **Planning** - Plan release strategy and testing
3. **Execution** - Prepare and deploy release
4. **Review** - QA validates release across platforms
5. **Summary** - Document release notes and outcomes

## Skills

- **ios-development** - Swift, SwiftUI, UIKit, iOS frameworks, App Store guidelines
- **android-development** - Kotlin, Jetpack Compose, Android Jetpack libraries, Material Design 3
- **cross-platform** - React Native, Flutter, cross-platform architecture, native bridges
- **mobile-testing** - Device testing, UI testing frameworks, performance testing, accessibility

## Telemetry

Tool usage is logged to `~/.claude/team-logs/mobile-dev.jsonl` for observability.

## Dependencies

This team focuses on agents and commands. For MCP integrations, install separately:

```bash
claude plugin install xcode        # Xcode integration
claude plugin install android-sdk  # Android SDK tools
claude plugin install react-native # React Native CLI
claude plugin install flutter      # Flutter CLI
claude plugin install appium       # Appium for testing
claude plugin install firebase     # Firebase CLI for deployment
```
