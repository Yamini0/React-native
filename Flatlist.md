# FlatList in React-Native

A performant interface for rendering basic, flat lists, supporting the most handy features:

- Fully cross-platform.
- Optional horizontal mode.
- Configurable viewability callbacks.
- Header support.
- Footer support.
- Separator support.
- Pull to Refresh.
- Scroll loading.
- ScrollToIndex support.
- Multiple column support.

```
<SafeAreaView>
      <FlatList
        data={abc.data}
        keyExtractor={ }
        renderItem={ }
        refreshing={ }
        onRefresh={ }
        .
        .
      />
    </SafeAreaView>
```

## Features of Flatlist:

1. **renderItem:**Takes an item from data and renders it into the list.

```
renderItem={({ item, index, separators }) => (
    <TouchableHighlight
      key={item.key}
      onPress={() => this._onPress(item)}
      onShowUnderlay={separators.highlight}
      onHideUnderlay={separators.unhighlight}>
      <View style={{ backgroundColor: 'white' }}>
        <Text>{item.title}</Text>
      </View>
    </TouchableHighlight>
  )}
```

- item (Object): The item from data being rendered.
- index (number): The index corresponding to this item in the data array.
- separators (Object)
  - highlight (Function)
  - unhighlight (Function)
  - updateProps (Function)
    - select (enum('leading', 'trailing'))
    - newProps (Object)

2. **data:**For simplicity, data is a plain array. If you want to use something else, like an immutable list, use the underlying VirtualizedList directly.

3. **ItemSeparatorComponent**
   Rendered in between each item, but not at the top or bottom. By default, highlighted and leadingItem props are provided. renderItem provides separators.highlight/unhighlight which will update the highlighted prop, but you can also add custom props with separators.updateProps.

4.**ListEmptyComponent**
Rendered when the list is empty. Can be a React Component (e.g. SomeComponent), or a React element (e.g. <SomeComponent />).

5. **ListFooterComponent:**
   Rendered at the bottom of all the items. Can be a React Component (e.g. SomeComponent), or a React element (e.g. <SomeComponent />).

6. **ListHeaderComponent:**
   Rendered at the top of all the items. Can be a React Component (e.g. SomeComponent), or a React element (e.g. <SomeComponent />).

7. **extraData:**
   A marker property for telling the list to re-render (since it implements PureComponent). If any of your renderItem, Header, Footer, etc. functions depend on anything outside of the data prop, stick it here and treat it immutably.

8. **keyExtractor:**
   Used to extract a unique key for a given item at the specified index. Key is used for caching and as the react key to track item re-ordering. The default extractor checks item.key, then item.id, and then falls back to using the index, like React does.

`keyExtractor={(item: object, index: number) => string};`

9. **onEndReached:**
   Called once when the scroll position gets within onEndReachedThreshold of the rendered content.

10. **onRefresh:**
    If provided, a standard RefreshControl will be added for "Pull to Refresh" functionality. Make sure to also set the refreshing prop correctly.

11. **refreshing:**
    Set this true while waiting for new data from a refresh. `refreshing={true}`
