# Navigation in React-Native

React Navigation is a popular library for routing and navigation in a React Native application.

This library helps solve the problem of navigating between multiple screens and sharing data between them.

## StackNavigation

For navigating between screens, you will use a StackNavigator. A StackNavigator works exactly like a call stack. Each screen you navigate to is pushed to the top of the stack. Each time you hit the back button, the screens pop off the top of the stack.

**Installation** :

1.  Install @react-navigation/native:

    `npm install @react-navigation/native`

2.  Install @react-navigation/stack and its peer dependencies:

    `npm install @react-navigation/stack @react-native-community/masked-view react-native-screens react-native-safe-area-context react-native-gesture-handler`

3.  Add NavigationContainer and createStackNavigation to your Ap.js :
    `import { NavigationContainer } from '@react-navigation/native'; import { createStackNavigator } from '@react-navigation/stack';`
    Inside createStackNavigation you should define your Screens with the screen name like:

    ![](image/4.png)

4.  Using **Context** to pass Data to other Screens
