---
title: React native 101 
date: 2024-07-01 23:39:50
tags: React
categories: 
   - Frontend
   - React

---

# Pro of React native
- Transferable knowledge of React, reduce the learning curve
- Native components -> Better performance
- More seamless UX
- Cross-platform compatibility

# Things will be explored
1. Basic Element
   - View
   - Touchable
   - Image
   - Flatlist
   - ScrollView
   - SafeAreaView
   - TextInput
   - StatusBar 

2. react-native-animatable
3. responsive design
4. style sheet + Tailwind CSS for styling
5. file based and dynamic routing (nested route + layout, Next js alike)

![](https://github.com/Owen771/Owen771.github.io/assets/66254587/1bd69828-2575-4b63-a56f-3a975cc33634)

# A mapping from react to specific platforms
![](https://github.com/Owen771/Owen771.github.io/assets/66254587/7d10eff0-ffe3-4e09-b9e0-cea10fe7f145)


## Text
web: <p>, <h1>
mobile: <Text>

- StyleSheet: define style via a js obj, and it optimizes performance
- NativeWind: a style lib, mobile version of Tailwind


`<View>` is like `<div>`, act as a container that holds other comp 


- Buttons, Links, Other interactive elem can be impl via 
  - TouchableOpacity
  - TouchableHighlight
  - TouchableWithoutFeedback (useful for links or images)

- ActivityIndictor: allow u to show a loading indicator
- Flatlist: use for rendering a long list of items that need to be scrolled efficiently
  - for smaller list can just Map func like React

- ScrollView: hold multiple comp and views, and providing a scrolling container for them
- SafeAreaView: provide a safe zone to render app content without being covered by device hardware like home indicator or status bar
  - it's great for app that are supported on devices with diff screen size and shape



## app.json

- scheme: for deep link, can be app name
- slug:  url friendly version of app name




























