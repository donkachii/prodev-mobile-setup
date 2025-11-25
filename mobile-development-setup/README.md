# Mobile Development Setup: Expo & React Native

This document outlines the setup process for Expo and React Native development environment, including prerequisites, installation steps, and challenges encountered during setup.

## Prerequisites

### System Requirements
- **Operating System**: macOS (recommended), Windows, or Linux
- **Node.js**: Version 18 or later
- **npm** or **yarn**: Package manager
- **Git**: Version control system
- **Xcode** (macOS only): Required for iOS development
- **Android Studio**: Required for Android development (optional for Expo Go testing)

### Hardware Requirements
- **RAM**: Minimum 8GB, recommended 16GB+
- **Storage**: At least 10GB free space
- **Internet Connection**: Stable connection for package downloads

## Installation Steps

### 1. Node.js Installation

```bash
# Check if Node.js is installed
node --version
npm --version

# If not installed, install via nvm (recommended)
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash
source ~/.bashrc
nvm install node
nvm use node
```

### 2. Expo CLI Installation

```bash
# Install Expo CLI globally
npm install -g @expo/cli

# Verify installation
expo --version
```

### 3. Create New Expo Project

```bash
# Create a new Expo project
npx create-expo-app@latest MyApp

# Navigate to project directory
cd MyApp

# Start the development server
npx expo start
```

### 4. Additional Development Tools

```bash
# Install React Native CLI (optional, for bare workflow)
npm install -g @react-native-community/cli

# Install watchman (macOS performance improvement)
brew install watchman
```

## Development Environment Setup

### iOS Development (macOS only)
1. Install Xcode from App Store
2. Install Xcode Command Line Tools:
   ```bash
   xcode-select --install
   ```
3. Accept Xcode license:
   ```bash
   sudo xcodebuild -license accept
   ```

### Android Development
1. Download and install Android Studio
2. Install Android SDK components via SDK Manager
3. Set up environment variables:
   ```bash
   export ANDROID_HOME=$HOME/Library/Android/sdk
   export PATH=$PATH:$ANDROID_HOME/emulator
   export PATH=$PATH:$ANDROID_HOME/tools
   export PATH=$PATH:$ANDROID_HOME/tools/bin
   export PATH=$PATH:$ANDROID_HOME/platform-tools
   ```

## Testing Your Setup

### Using Expo Go App
1. Install Expo Go on your physical device from App Store/Play Store
2. Scan the QR code displayed in terminal after running `npx expo start`
3. Your app should load on the device

### Using Simulators/Emulators
```bash
# iOS Simulator (macOS only)
npx expo start --ios

# Android Emulator
npx expo start --android
```

## Common Challenges and Solutions

### Challenge 1: Node Version Conflicts
**Issue**: Multiple Node.js versions causing compatibility issues
**Solution**:
```bash
# Use nvm to manage versions
nvm list
nvm use 18
```

### Challenge 2: Xcode Command Line Tools Issues
**Issue**: Xcode tools not found or outdated
**Solution**:
```bash
# Reinstall command line tools
sudo rm -rf /Library/Developer/CommandLineTools
xcode-select --install
```

### Challenge 3: Android SDK Path Issues
**Issue**: Android SDK not found in PATH
**Solution**: Add to your shell profile (~/.zshrc or ~/.bashrc):
```bash
export ANDROID_HOME=$HOME/Library/Android/sdk
export PATH=$PATH:$ANDROID_HOME/platform-tools
```

### Challenge 4: Metro Bundler Issues
**Issue**: Development server fails to start or crashes
**Solution**:
```bash
# Clear Metro cache
npx expo start --clear

# Or manually clear cache
rm -rf node_modules/.cache
```

### Challenge 5: Permission Issues
**Issue**: npm install fails due to permission errors
**Solution**:
```bash
# Use npx instead of global installs, or fix permissions
sudo chown -R $(whoami) ~/.npm
```

### Challenge 6: Network/Firewall Issues
**Issue**: Package downloads blocked by firewall
**Solution**:
- Configure proxy settings
- Use VPN if necessary
- Check corporate network restrictions

## Project Structure

After successful setup, your project should have the following structure:

```
MyApp/
├── app/
│   ├── _layout.tsx
│   ├── index.tsx
│   └── +html.tsx
├── assets/
│   ├── fonts/
│   └── images/
├── components/
├── constants/
├── hooks/
├── node_modules/
├── app.json
├── package.json
├── tsconfig.json
└── README.md
```

## Development Workflow

1. **Start Development Server**: `npx expo start`
2. **Run on Device/Emulator**: Press appropriate keys (iOS: `i`, Android: `a`)
3. **Reload App**: Press `r` in terminal or shake device for dev menu
4. **Build Production App**: `npx expo build:android` or `npx expo build:ios`

## Troubleshooting

### Getting Help
- **Expo Documentation**: https://docs.expo.dev/
- **React Native Documentation**: https://reactnative.dev/docs/getting-started
- **Expo Forums**: https://forums.expo.dev/
- **Stack Overflow**: Search for [expo] or [react-native] tags

### Useful Commands
```bash
# Check Expo diagnostics
npx expo diagnostics

# Clear all caches
npx expo start --clear

# Reset Metro bundler
rm -rf node_modules && npm install
```

## Next Steps

After successful setup:
1. Learn React Native fundamentals
2. Explore Expo SDK components
3. Set up version control (Git)
4. Configure CI/CD pipeline
5. Deploy your first app

---

*Last updated: November 2025*
*Setup completed on: [Date]*
*Environment: macOS [version]*
