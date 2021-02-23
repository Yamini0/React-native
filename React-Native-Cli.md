# React-Native CLI

Its is best for those who are fimilar with mobile development, It requires Xcode or Android Studio to get started. If you already have one of these tools installed, you should be able to get up and running within a few minutes. If they are not installed, you should expect to spend about an hour installing and configuring them.

You will need Node, the React Native command line interface, a JDK, and Android Studio.

While you can use any editor of your choice to develop your app, you will need to install Android Studio in order to set up the necessary tooling to build your React Native app for Android.

# React-native command line interface

React Native has a built-in command line interface. Rather than install and manage a specific version of the CLI globally, we recommend you access the current version at runtime using npx, which ships with Node.js. With npx react-native <command>, the current stable version of the CLI will be downloaded and executed at the time the command is run.

## Starting with the project

1. Previously we download a global _react-native-cli_ package. with command:

`npm install -g react-native-cli`

2. Starting with the project :

`react-native init [projectname]`

It will download all the requried libraries for your project.

Now open the Created Project folder and start coding.
To see your application on the virtual device, go through these commands:

1. In CMD run

`npm react-native start`

It will start the metro Bundler.

**NOTE:**

- To run Application directly on android emulator, go for this command:

`npm react-native run-android`

- To run Application directly on ios emulator, go for this command:

`npm react-native run-ios`
