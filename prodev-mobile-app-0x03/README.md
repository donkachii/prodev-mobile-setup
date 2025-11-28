# ProDev Mobile App - React Native Setup Documentation

This document captures the setup process, configuration, and challenges encountered while setting up this React Native application using Expo.

## Project Overview

This is a React Native mobile application built with [Expo](https://expo.dev) and created using [`create-expo-app`](https://www.npmjs.com/package/create-expo-app). The project uses Expo Router for file-based routing and supports iOS, Android, and web platforms.

## Environment Setup

### System Information
- **Operating System**: macOS
- **Node.js Version**: v23.7.0
- **npm Version**: 11.5.2
- **Expo Version**: ~54.0.25
- **React Native Version**: 0.81.5
- **React Version**: 19.1.0

### Prerequisites Installed

Before starting this project, the following tools were installed:

1. **Node.js and npm**
   ```bash
   node --version  # v23.7.0
   npm --version   # 11.5.2
   ```

2. **Expo CLI**
   ```bash
   npx expo --version  # 54.0.16
   ```

3. **Additional Tools**
   - Git for version control
   - CocoaPods (via Homebrew) for iOS dependencies
   - Xcode (for iOS development)

## Project Setup Steps

### 1. Initial Project Creation

The project was created using the latest Expo template:

```bash
npx create-expo-app@latest .
```

This command initialized the project in the current directory with:
- Expo Router for navigation
- TypeScript configuration
- File-based routing structure
- Default assets and configurations

### 2. Project Structure

The created project has the following structure:

```
prodev-mobile-app-0x02/
├── app/                    # File-based routing directory
│   ├── _layout.tsx        # Root layout
│   └── index.tsx          # Home screen
├── assets/                # Images, fonts, and static files
│   └── images/
├── node_modules/          # Dependencies
├── .expo/                 # Expo configuration cache
├── .vscode/               # VS Code settings
├── app.json               # Expo configuration
├── package.json           # Dependencies and scripts
├── tsconfig.json          # TypeScript configuration
├── eslint.config.js       # ESLint configuration
└── README.md              # This file
```

### 3. Dependencies Installed

Key dependencies in this project:

**Core Libraries:**
- `expo` (~54.0.25) - Expo SDK
- `react` (19.1.0) - React library
- `react-native` (0.81.5) - React Native framework
- `expo-router` (~6.0.15) - File-based routing

**Navigation:**
- `@react-navigation/native` (^7.1.8)
- `@react-navigation/bottom-tabs` (^7.4.0)
- `react-native-screens` (~4.16.0)
- `react-native-safe-area-context` (~5.6.0)

**UI Components:**
- `@expo/vector-icons` (^15.0.3)
- `expo-symbols` (~1.0.7)
- `expo-image` (~3.0.10)

**Animations:**
- `react-native-reanimated` (~4.1.1)
- `react-native-gesture-handler` (~2.28.0)
- `react-native-worklets` (0.5.1)

**Development Tools:**
- `typescript` (~5.9.2)
- `eslint` (^9.25.0)
- `@types/react` (~19.1.0)

### 4. Configuration Highlights

Key configurations in `app.json`:

```json
{
  "newArchEnabled": true,           // Using React Native's new architecture
  "experiments": {
    "typedRoutes": true,            // Type-safe routing
    "reactCompiler": true           // React Compiler experimental feature
  }
}
```

## Development Workflow

### Starting the Development Server

```bash
npm start
# or
npx expo start
```

### Running on Different Platforms

```bash
# iOS Simulator
npm run ios
# or press 'i' in the terminal after starting

# Android Emulator
npm run android
# or press 'a' in the terminal after starting

# Web Browser
npm run web
# or press 'w' in the terminal after starting
```

### Development Options

After starting the development server, you can:
- Scan the QR code with Expo Go app on your physical device
- Press `i` to open iOS Simulator (macOS only)
- Press `a` to open Android Emulator
- Press `w` to open in web browser
- Press `r` to reload the app
- Press `m` to toggle menu

## Challenges Encountered

### Challenge 1: Project Reset Understanding

**Issue**: Initially ran `npm run reset-project` multiple times to understand its purpose.

**What Happened**:
- The reset script moves the starter code to `app-example/` directory
- Creates a blank `app/` directory for custom development
- Attempted this command 3 times while learning the project structure

**Resolution**: 
- Understood that this command is optional and only needed when starting from scratch
- Kept the default starter code for learning purposes

### Challenge 2: Directory Navigation

**Issue**: Working with multiple project versions (0x00, 0x01, 0x02) in the same parent directory.

**Solution**:
- Organized projects in a clear directory structure
- Used descriptive naming conventions (prodev-mobile-app-0x00, 0x01, 0x02)
- Maintained separate git commits for each iteration

### Challenge 3: Understanding Expo Router

**Issue**: File-based routing was a new concept coming from traditional React Navigation.

**Learning Points**:
- Files in `app/` directory automatically become routes
- `_layout.tsx` files define nested layouts
- Type-safe routing with experimental `typedRoutes` feature
- Seamless integration with React Navigation under the hood

### Challenge 4: New Architecture and Experimental Features

**Issue**: Project uses React Native's new architecture and experimental React Compiler.

**Considerations**:
- `newArchEnabled: true` enables Fabric renderer and TurboModules
- May have compatibility issues with some third-party libraries
- React Compiler is experimental but improves performance
- Stayed with defaults to learn modern best practices

## Git Workflow

Project commits:
```
89bd643 - feat: add styles to texts
0a00a21 - feat: add mobile app
802ad5b - feat: add expo app
851a0d0 - feat: setup project
c0209c0 - Initial commit
```

## Available Scripts

```bash
# Start development server
npm start

# Run on specific platform
npm run ios
npm run android
npm run web

# Linting
npm run lint

# Reset project to blank slate
npm run reset-project
```

## Learning Resources

### Official Documentation
- [Expo Documentation](https://docs.expo.dev/) - Comprehensive guides and API reference
- [React Native Documentation](https://reactnative.dev/) - Core concepts and components
- [Expo Router Documentation](https://docs.expo.dev/router/introduction/) - File-based routing

### Tutorials
- [Learn Expo Tutorial](https://docs.expo.dev/tutorial/introduction/) - Official step-by-step guide
- [React Native Express](http://www.reactnative.express/) - Interactive learning platform

### Community
- [Expo Discord](https://chat.expo.dev) - Active community support
- [Expo Forums](https://forums.expo.dev/) - Discussion and Q&A
- [GitHub Issues](https://github.com/expo/expo) - Bug reports and feature requests

## Next Steps

- [ ] Complete Expo Router tutorial
- [ ] Add custom styling and theming
- [ ] Implement navigation between screens
- [ ] Add API integration
- [ ] Set up state management (Context API or Redux)
- [ ] Test on physical devices
- [ ] Configure app icons and splash screens
- [ ] Prepare for production build

## Useful Commands

```bash
# Clear Expo cache
npx expo start --clear

# Check for Expo updates
npx expo install --check

# Upgrade Expo SDK
npx expo install expo@latest

# Run TypeScript type checking
npx tsc --noEmit

# Run linter
npm run lint
```

## Notes

- This project uses the new React Native architecture for better performance
- TypeScript is configured for type safety
- File-based routing simplifies navigation structure
- Expo Go app can be used for quick testing without building native code
- For production, will need to create development builds or use EAS Build

---

**Setup Date**: November 25, 2025  
**Last Updated**: November 28, 2025  
**Platform**: macOS with Apple Silicon  
**Status**: ✅ Development environment ready
