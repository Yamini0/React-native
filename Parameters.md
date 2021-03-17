# Inheriting Parameters with React Navigation

we know how to make use different navigations, Lets take a look how we can pass data between them when we navigate to them.

The procedure is simple and just includes 2 steps to follow:

1. pass the param alias for parameter to a route by putting them in an object as a 2nd parameter to `navigation.navigate` function. like :

`navigation.navigate('RouteName',{params})`.

2. Make read the param in the screen component where you want the param, like:`route.params`.

It is recommented to pass the params should be JSON-serialiable. which means, the object we pass should be converted in the string. that will able us to use state persistence.

Example Code:

- HomeScreen: where params are passed

```
function HomeScreen({ navigation }) {
  return (
    <View style={{ flex: 1, alignItems: 'center', justifyContent: 'center' }}>
      <Text>Home Screen</Text>
      <Button
        title="Go to Details"
        onPress={() => {
          /* Navigate to the Details route with params */
          navigation.navigate('Details', {
            Param: 'anything you want here',
          });
        }}
      />
    </View>
  );
}
```

- DetailScreen: where params are gotten

```
function DetailsScreen({ route, navigation }) {
  /* 2. Get the param */
  const { Param } = route.params; //name should be the same
  return (
      <View>
      <Text>Details Screen</Text>
      <Text>Param: {JSON.stringify(Param)}</Text>
    </View>
  );
}
```

## How to know what should be in param?

It's important to understand what kind of data should be in params. Params are like options for a screen. They should only contain information to configure what's displayed in the screen. Avoid passing the full data which will be displayed on the screen itself (e.g. pass an user id instead of user object). Also avoid passing data which is used by multiple screens, such data should be in a global store.

If the user object isn't passed, or improperly formatted, this could result in crashes as the screen won't know how to handle it.

Params should contain the minimal data required to show a screen, nothing more

## Initial params

Let consider an scenario, we forget or didn't specify any params when navigating to the screen, in this case the concept of `initialParams` comes to game.
We can pass some params to a screen when initialed (when we declare it in stack navigation). For Example:

```
<Stack.Screen
  name="Details"
  component={DetailsScreen}
  initialParams={{ itemId: 42 }}
/>
```

By initializing `initialParams` when screen is initialised, these are used when we navigate between the screen.

## Update the screens params : setParams

Like the states can be updated in a screen, params can also be updated. The `navigation.setParams` method let us to update the param of a screen.
