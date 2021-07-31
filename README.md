# List of things during a project setup

## List of dev dependencies

### React Native - TS variant

- Project Setup
```bash
yarn add @babel/core @babel/runtime @react-native-community/eslint-config @types/jest @types/react-native @types/react-test-renderer @typescript-eslint/parser babel-jest eslint eslint-config-airbnb-base eslint-import-resolver-typescript eslint-plugin-import jest metro-react-native-babel-preset react-test-renderer typescript -D
```

## List of dependencies

### React Native - TS variant

- Animations
```bash
yarn add react-native-reanimated
```


## Monorepo setup - react-native, react, core


### Most common errors

- version mistmatches in package.json in all the packages. All the dependencies should have the same verison
- Wrong node modules path in the mobile app native ios and android configs.
- while building ios, react-native directory won't be found in mobile/node_modules
- android builds might fail because of gradle versions

### Solutions
- make all versions the same and use lerna to manage the installation of node_modules
- rectify all node_module paths inside the native ios and android configs
- make sure that all the paths for react native in the Podfile have been changed and then run `npx pod-install`
- Do the following in case of failed builds:
  - Go to `android/gradle/wrapper/gradle-wrapper.properties`, and change the value of `distributionUrl` to `https\://services.gradle.org/distributions/gradle-6.7.1-bin.zip` like  this `distributionUrl=https\://services.gradle.org/distributions/gradle-6.7.1-bin.zip`
  - Download JDK 11 and set your `$JAVA_HOME` variable to JDK 11

### Tips
- To get a list of emulators; run this command: `emulator -list-avds`
- To increase performance of emulator; run this command:  `emulator -gpu host -feature HVF -avd <name-of-avd-from-list>`
- If you want to change the JDK version in android studio: [answer for this](https://stackoverflow.com/a/67414820/7879090)

### References
- [Edits to be made in cofig files](https://medium.com/@ratebseirawan/react-native-0-63-monorepo-walkthrough-36ea27d95e26)
