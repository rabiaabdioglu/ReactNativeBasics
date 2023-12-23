- [React Native](#react-native)
  - [Introduction to React Native](#introduction-to-react-native)
  - [Setting Up a React Native Development Environment](#setting-up-a-react-native-development-environment)
  - [Creating Your First React Native Project](#creating-your-first-react-native-project)
  - [React Native Project Structure](#react-native-project-structure)
  - [Building User Interfaces with React Native Components](#building-user-interfaces-with-react-native-components)
  - [Styling in React Native](#styling-in-react-native)
  - [Component in ReactNative](#component-in-reactnative)
  - [SectionList](#sectionlist)
  - [Simple LoginPage UI](#simple-loginpage-ui)
  - [Pressable Usage](#pressable-usage)
  - [Managing Navigation in React Native](#managing-navigation-in-react-native)
    - [Stack Navigation](#stack-navigation)
    - [Tab Navigation](#tab-navigation)
    - [Drawer Navigation](#drawer-navigation)


## React Native
#### Introduction to React Native

###### React Native is an open-source framework developed by Facebook that enables you to build iOS and Android mobile applications using JavaScript and React. React Native allows you to create applications for both iOS and Android platforms using the same codebase, which speeds up development and reduces costs.

###### The key advantages of developing applications with React Native include:

###### 1- Single Codebase: You can develop both iOS and Android applications using the same JavaScript and React code.

###### 2- Performance: React Native delivers fast and smooth performance on mobile devices because the application operates like a native app.

###### 3- Rapid Development: It provides a rapid development cycle, allowing you to view your code instantly and test quickly.

###### 4- Community and Ecosystem: With a large community and a useful ecosystem, finding ready-made components and modules is easy.





#### Setting Up a React Native Development Environment

###### Setting up a development environment for React Native is the first step towards building powerful mobile applications for both iOS and Android platforms. In this guide, we'll take you through the process of configuring your system to get you up and running with React Native development.

#### Prerequisites
###### Before diving into React Native development, you should have a few prerequisites in place:

###### Node.js and npm: Ensure you have Node.js installed on your machine. You can download it from the official website.

###### Expo CLI (optional): Expo is a set of tools and services built around React Native, which can make the development process even easier.
###### You can install Expo CLI globally by running
```javascript
 npm install -g expo-cli.
```
###### Android Studio (for Android development): If you plan to develop for Android, you'll need to install Android Studio.

###### Xcode (for iOS development): For iOS development, you'll need Xcode, which is available on the Mac App Store.

#### Creating Your First React Native Project
###### Now that your environment is set up, it's time to create your first React Native project. We'll use the react-native command-line tool to generate a new project.
###### Open your terminal and run the following command to create a new React Native project:

```javascript

npx react-native init YourProjectName
```

###### Replace YourProjectName with the desired name for your project. Wait for the project to be initialized. This may take a few minutes.

###### Once the project is created, navigate to its directory:

```javascript

cd YourProjectName
```

###### To start your React Native app, run:

```javascript

npx react-native run-android
// or

npx react-native run-ios
```

#### React Native Project Structure
###### Understanding the project structure is crucial for effective development in React Native. Let's take a quick look at the key directories and files that make up a typical React Native project:

###### android/ and ios/: These directories contain the native code for Android and iOS, respectively. You'll rarely need to touch these files directly.

###### node_modules/: This is where all your project's dependencies are stored. You don't need to manage this folder manually; it's generated and updated automatically.

###### App.js or index.js: These files serve as the entry points for your React Native app. You'll define your app's components and logic here.

###### package.json: This file holds project metadata and lists all the dependencies. You can add, remove, or update packages here.

###### metro.config.js: This configuration file for the Metro bundler allows you to customize how your JavaScript code is bundled and transformed.

###### assets/: This directory is used for static assets like images, fonts, and other resources.

###### **android/app/src/main and ios/YourProjectName (iOS): These directories contain configuration files specific to each platform.


#### Building User Interfaces with React Native Components


###### View: This is like a div in web development. It's a container for other components and is used for layout purposes.

###### Text: The Text component is used for displaying text. You can style it with fonts, colors, and more.

###### Image: To display images in your app, you'll use the Image component. You can load images from local files or the web.

###### Button: Creating buttons is easy with the Button component. You can add functionality to buttons using event handlers.

###### TextInput: The TextInput component allows users to input text. You can use it for things like login forms or search bars.

###### ScrollView and FlatList: These components are used for displaying lists of data. FlatList is more efficient for long lists.


```javascript
import React from 'react';
import { View, Text, Image, Button, TextInput } from 'react-native';

const App = () => {
  return (
    <View>
      <Text>Hello, React Native!</Text>
      <Image source={{ uri: 'https://example.com/image.jpg' }} />
      <Button title="Click Me" onPress={() => alert('Button Clicked!')} />
      <TextInput placeholder="Enter Text" onChangeText={(text) => console.log(text)} />
    </View>
  );
};

export default App;

```
###### ScrollView:  allows you to create a region on the screen that can be scrolled up and down. 

```javascript

import React from 'react';
import { ScrollView, Text } from 'react-native';

const App = () => {
  return (
    <ScrollView>
      <Text style={{ fontSize: 20 }}>Sample Text 1</Text>
      <Text style={{ fontSize: 20 }}>Sample Text 2</Text>
      <Text style={{ fontSize: 20 }}>Sample Text 3</Text>
      {/* ... You can add more text elements */}
    </ScrollView>
  );
};

export default App;

```
###### FlatList:  is used to efficiently display large lists of data. 

```javascript

import React from 'react';
import { FlatList, Text, View } from 'react-native';

const data = [
  { id: '1', title: 'Item 1' },
  { id: '2', title: 'Item 2' },
  { id: '3', title: 'Item 3' },
  // ... You can add more items
];

const App = () => {
  return (
    <FlatList
      data={data}
      keyExtractor={(item) => item.id}
      renderItem={({ item }) => (
        <View style={{ padding: 10 }}>
          <Text style={{ fontSize: 18 }}>{item.title}</Text>
        </View>
      )}
    />
  );
};

export default App;

```

#### Styling in React Native
Styling in React Native is similar to web development, but it uses a subset of CSS properties. You can apply styles directly to components using the style prop. Here are some key concepts:

###### Stylesheet: React Native encourages the use of a StyleSheet object to define styles. This provides better performance as styles are optimized during compilation.

###### Flexbox: React Native relies heavily on flexbox for layout. Understanding flex properties like flexDirection, justifyContent, and alignItems is crucial.

###### Absolute and Relative Positioning: You can use absolute positioning to precisely place elements. Relative positioning allows elements to flow naturally within the layout.

###### Responsive Design: React Native supports responsive design by adapting to different screen sizes and orientations.

```javascript
import React from 'react';
import { View, Text, StyleSheet } from 'react-native';

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: '#f0f0f0',
  },
  text: {
    fontSize: 24,
    color: 'blue',
  },
});

const App = () => {
  return (
    <View style={styles.container}>
      <Text style={styles.text}>Styled Text</Text>
    </View>
  );
};

export default App;

```


#### Component in ReactNative
###### Forms in React Native are created using various input components like TextInput, Picker, and Switch. To handle user input:



###### components > LittleLemonHeader.js
```javascript
import { View, Text } from 'react-native';

export default function Header() {
  return (
    <View style={{ flex: 0.15, backgroundColor: '#F4CE14' }}>
      <Text
        style={{
          padding: 40,
          fontSize: 30,
          color: 'black',
          textAlign: 'center',
        }}>
        HEADER
      </Text>
    </View>
  );
}

```
###### App.js

```javascript
import * as React from 'react';
import { View } from 'react-native';

import LittleLemonHeader from './components/Header';
export default function App() {
  return (
    <>
      <View
        style={{
          flex: 1,
          backgroundColor: 'pink',
        }}>
        <LittleLemonHeader />
      </View>
     
    </>
  );
}
```

#### View and Text Components
###### The nested Text component inherits all the properties and styling from the parent Text component. 
###### Notice that the number of visible lines have been set to 3 for the parent Text component. 
###### 'Flex' means that the header component will occupy 30 percent of the total space on the screen.  


```javascript
import * as React from 'react';
import { View, Text } from 'react-native';

export default function Header() {
  return (

    <View style={{ flex: 0.3, backgroundColor: 'pink' }}>
      <Text
        style={{ padding: 40, fontSize: 30, color: 'black' }}
        numberOfLines={3}>
        Welcome
        <Text style={{ fontWeight: 'bold' }}> Little Lemon</Text>     {' '}
      </Text>
    </View>
  );
}

```
#### StyleSheet API

###### component > MenuItems.js


```javascript
import React from 'react';
import { View, Text, ScrollView, StyleSheet } from 'react-native';

const techMenuItemsToDisplay = [
  'Smartphone \nLaptop \nSmartwatch \nGaming Console \nWireless Earbuds \nFitness Tracker \nVR Headset \nDrone \nRobot Vacuum \nBluetooth Speaker \nAction Camera \n3D Printer \nSmart Home Hub \nAugmented Reality Glasses \nFoldable Tablet \nPower Bank \nHigh-Performance Router \nSmart Refrigerator \nElectric Scooter \nAI-Powered Camera',
];

const TechMenuItems = () => {
  return (
    <View style={techMenuStyles.container}>
      <ScrollView
        horizontal={false}
        indicatorStyle={'white'}
        style={techMenuStyles.innerContainer}>
        <Text style={techMenuStyles.headerText}>Tech Menu</Text>
        <Text style={techMenuStyles.itemText}>{techMenuItemsToDisplay[0]}</Text>
      </ScrollView>
    </View>
  );
};

const techMenuStyles = StyleSheet.create({
  container: {
    flex: 0.75,
  },
  innerContainer: {
    paddingHorizontal: 40,
    paddingVertical: 40,
    backgroundColor: 'black',
  },
  headerText: {
    color: 'white',
    fontSize: 40,
    flexWrap: 'wrap',
  },
  itemText: {
    color: '#F4CE14',
    fontSize: 36,
  },
});

export default TechMenuItems;

```

#### SectionList 

###### component > MenuItems.js


```javascript


import React from 'react';
import { View, Text, StyleSheet, SectionList } from 'react-native';

// Array of technological items grouped by categories
const techItemsToDisplay = [
  {
    title: 'Smartphones',
    data: ['iPhone 13', 'Samsung Galaxy S21', 'Google Pixel 6', 'OnePlus 9'],
  },
  {
    title: 'Laptops',
    data: ['MacBook Pro', 'Dell XPS 13', 'HP Spectre x360', 'Surface Laptop 4'],
  },
  {
    title: 'Wearables',
    data: ['Apple Watch Series 7', 'Samsung Galaxy Watch 4', 'Fitbit Charge 5'],
  },
  {
    title: 'Smart Home',
    data: ['Amazon Echo', 'Google Nest Hub', 'Philips Hue Lights', 'Ring Doorbell'],
  },
];

// Component for rendering each item
const TechItem = ({ name }) => (
  <View style={techMenuStyles.innerContainer}>
    <Text style={techMenuStyles.itemText}>{name}</Text>
  </View>
);

// Component for rendering the separator between items
const TechSeparator = () => <View style={techMenuStyles.separator} />;

// Component for rendering the footer
const TechFooter = () => (
  <Text style={techMenuStyles.footerText}>© TechHub 2023. All Rights Reserved</Text>
);

// Main component for rendering the technology menu items
const TechMenuItems = () => {
  // Function to render each item
  const renderItem = ({ item }) => <TechItem name={item} />;

  // Function to render section headers
  const renderSectionHeader = ({ section: { title } }) => (
    <Text style={techMenuStyles.sectionHeader}>{title}</Text>
  );

  return (
    <View style={techMenuStyles.container}>
      {/* SectionList component to display the technology items */}
      <SectionList
        keyExtractor={(item, index) => item + index}
        sections={techItemsToDisplay}
        renderItem={renderItem}
        renderSectionHeader={renderSectionHeader}
        ListFooterComponent={TechFooter}
        ItemSeparatorComponent={TechSeparator}
      />
    </View>
  );
};

// Styles for the technology menu component
const techMenuStyles = StyleSheet.create({
  container: {
    flex: 0.95,
  },
  innerContainer: {
    paddingHorizontal: 40,
    paddingVertical: 20,
    backgroundColor: '#333333',
  },
  sectionHeader: {
    backgroundColor: '#fbdabb',
    color: '#333333',
    fontSize: 34,
    flexWrap: 'wrap',
    textAlign: 'center',
  },
  itemText: {
    color: '#F4CE14',
    fontSize: 32,
  },
  separator: {
    borderBottomWidth: 1,
    borderColor: '#EDEFEE',
  },
  footerText: {
    color: '#EDEFEE',
    fontSize: 20,
    flexWrap: 'wrap',
    textAlign: 'center',
  },
});

export default TechMenuItems;
```

#### Simple LoginPage UI 

###### 


```javascript

import React, { useState } from 'react';
import { ScrollView, Text, StyleSheet, TextInput, Pressable } from 'react-native';

export default function RegisterScreen() {
  const [name, onChangeName] = useState('');
  const [email, onChangeEmail] = useState('');
  const [password, onChangePassword] = useState('');

  const handleRegister = () => {
    // Burada kayıt işlemleri yapılabilir
    console.log('Name:', name);
    console.log('Email:', email);
    console.log('Password:', password);
    // Kayıt işlemleri burada yapılabilir
  };

  return (
    <ScrollView style={styles.container}>
      <Text style={styles.headerText}>Create an Account</Text>
      <TextInput
        style={styles.inputBox}
        value={name}
        onChangeText={onChangeName}
        placeholder={'Name'}
        keyboardType={'default'}
      />
      <TextInput
        style={styles.inputBox}
        value={email}
        onChangeText={onChangeEmail}
        placeholder={'Email'}
        keyboardType={'email-address'}
      />
      <TextInput
        style={styles.inputBox}
        value={password}
        onChangeText={onChangePassword}
        placeholder={'Password'}
        keyboardType={'default'}
        secureTextEntry={true}
      />
      <Pressable style={styles.registerButton} onPress={handleRegister}>
        <Text style={styles.buttonText}>Register</Text>
      </Pressable>
    </ScrollView>
  );
}

// Styles for the technology menu component ...

```

#### Pressable Usage

###### 


```javascript


import React, { useState } from 'react';
import { View, Text, StyleSheet, SectionList, Pressable } from 'react-native';

const techItemsToDisplay = [
  {
    title: 'Smartphones',
    data: ['iPhone 13', 'Samsung Galaxy S21', 'Google Pixel 6', 'OnePlus 9'],
  },
  {
    title: 'Laptops',
    data: ['MacBook Pro', 'Dell XPS 13', 'HP Spectre x360', 'Surface Laptop 4'],
  },
  {
    title: 'Wearables',
    data: ['Apple Watch Series 7', 'Samsung Galaxy Watch 4', 'Fitbit Charge 5'],
  },
  {
    title: 'Smart Home',
    data: ['Amazon Echo', 'Google Nest Hub', 'Philips Hue Lights', 'Ring Doorbell'],
  },
];

const Separator = () => <View style={techMenuStyles.separator} />;

const Footer = () => (
  <Text style={techMenuStyles.footerText}>© TechHub 2023. All Rights Reserved</Text>
);

const TechItem = ({ name }) => (
  <View style={techMenuStyles.innerContainer}>
    <Text style={techMenuStyles.itemText}>{name}</Text>
  </View>
);

const TechMenu = () => {
  const [showMenu, setShowMenu] = useState(false);

  const renderItem = ({ item }) => <TechItem name={item} />;

  const renderSectionHeader = ({ section: { title } }) => (
    <Text style={techMenuStyles.sectionHeader}>{title}</Text>
  );

  return (
    <View style={techMenuStyles.container}>
      {!showMenu && (
        <Text style={techMenuStyles.infoSection}>
          Explore the latest and greatest in technology with TechHub. View our
          catalog of cutting-edge gadgets and devices!
        </Text>
      )}
      <Pressable
        style={techMenuStyles.button}
        onPress={() => setShowMenu((prevState) => !prevState)}>
        <Text style={techMenuStyles.buttonText}>
          {showMenu ? 'Home' : 'View Tech Menu'}
        </Text>
      </Pressable>
      {showMenu && (
        <SectionList
          keyExtractor={(item, index) => item + index}
          sections={techItemsToDisplay}
          renderItem={renderItem}
          renderSectionHeader={renderSectionHeader}
          ListFooterComponent={Footer}
          ItemSeparatorComponent={Separator}></SectionList>
      )}
    </View>
  );
};
// Styles for the technology menu component ...


export default TechMenu;


```

#### Managing Navigation in React Native
#### Stack Navigation


###### Passing props to Screen



###### screen > HomeScreen.js


```javascript

import React from 'react';
import { View, Text, Button } from 'react-native';

const HomeScreen = ({ navigation }) => {
  // Using the `navigation` prop to navigate to the Details screen
  const onPressHandler = () => {
    navigation.navigate('Details', { message: 'Hello from HomeScreen!' });
  };

  return (
    <View style={{ flex: 1, alignItems: 'center', justifyContent: 'center' }}>
      <Text>Home Screen</Text>
      <Button title="Go to Details" onPress={onPressHandler} />
    </View>
  );
};

export default HomeScreen;


```



###### screen > DetailScreen.js


```javascript

import React from 'react';
import { View, Text } from 'react-native';

const DetailsScreen = ({ route }) => {
  // Accessing and using parameters through the `route` prop
  const { message } = route.params;

  return (
    <View style={{ flex: 1, alignItems: 'center', justifyContent: 'center' }}>
      <Text>Details Screen</Text>
      <Text>{message}</Text>
    </View>
  );
};

export default DetailsScreen;


```



###### App.js


```javascript

import React from 'react';
import { NavigationContainer } from '@react-navigation/native';
import { createNativeStackNavigator } from '@react-navigation/native-stack';
import HomeScreen from './screens/HomeScreen';
import DetailsScreen from './screens/DetailsScreen';

const Stack = createNativeStackNavigator();

const App = () => {
  return (
    <NavigationContainer>
      <Stack.Navigator initialRouteName="Home">
        <Stack.Screen
          name="Home"
          component={HomeScreen}
        />
        {/* Defining parameters when navigating to the `DetailsScreen` */}
        <Stack.Screen
          name="Details"
          component={DetailsScreen}
          initialParams={{ message: 'Hello from initial params!' }}
        />
      </Stack.Navigator>
    </NavigationContainer>
  );
};

export default App;


```

#### Moving to a new screen through various methods

###### Navigate Hook


```javascript
import { useNavigation } from '@react-navigation/native';

const MyComponent = () => {
  const navigation = useNavigation();

  return (
    <Button
      title="Go to Details"
      onPress={() => navigation.navigate('Details')}
    />
  );
};

```

###### Navigation Prop


```javascript
import React from 'react';
import { Button } from 'react-native';

const MyComponent = ({ navigation }) => (
  <Button
    title="Go to Details"
    onPress={() => navigation.navigate('Details')}
  />
);

export default MyComponent;

```


###### withNavigation HOC


```javascript
import React from 'react';
import { withNavigation } from '@react-navigation/compat';
import { Button } from 'react-native';

const MyComponent = ({ navigation }) => (
  <Button
    title="Go to Details"
    onPress={() => navigation.navigate('Details')}
  />
);

export default withNavigation(MyComponent);

```

###### Navigation Actions 


```javascript
import { CommonActions, useNavigation } from '@react-navigation/native';
import { Pressable, Text } from 'react-native';

const MyComponent = () => {
  const navigation = useNavigation();

  const handlePress = () => {
    navigation.dispatch(CommonActions.navigate({ name: 'Details' }));
  };

  return (
    <Pressable onPress={handlePress}>
      <Text>Go to Details</Text>
    </Pressable>
  );
};

export default MyComponent;


```

#### Going Back to Previous Screen

###### goBack


```javascript
import { useNavigation } from '@react-navigation/native';
import { Button } from 'react-native';

const DetailsScreen = () => {
  const navigation = useNavigation();

  const handleGoBack = () => {
    navigation.goBack();
  };

  return (
    <Button title="Go Back" onPress={handleGoBack} />
  );
};

export default DetailsScreen;

```

###### navigation.navigate


```javascript
import { useNavigation } from '@react-navigation/native';
import { Button } from 'react-native';

const DetailsScreen = () => {
  const navigation = useNavigation();

  const handleGoBack = () => {
    navigation.navigate('PreviousScreen'); // Önceki sayfanın adını buraya ekleyin
  };

  return (
    <Button title="Go Back" onPress={handleGoBack} />
  );
};

export default DetailsScreen;

```


###### CommonActions.goBack


```javascript
import { CommonActions, useNavigation } from '@react-navigation/native';
import { Button } from 'react-native';

const DetailsScreen = () => {
  const navigation = useNavigation();

  const handleGoBack = () => {
    navigation.dispatch(CommonActions.goBack());
  };

  return (
    <Button title="Go Back" onPress={handleGoBack} />
  );
};

export default DetailsScreen;

```

#### Tab Navigation


```javascript


import React from 'react';
import { createBottomTabNavigator } from '@react-navigation/bottom-tabs';
import { NavigationContainer } from '@react-navigation/native';
import HomeScreen from './HomeScreen';
import ProfileScreen from './ProfileScreen';

const Tab = createBottomTabNavigator();

const App = () => {
  return (
    <NavigationContainer>
      <Tab.Navigator>
        <Tab.Screen name="Home" component={HomeScreen} />
        <Tab.Screen name="Profile" component={ProfileScreen} />
      </Tab.Navigator>
    </NavigationContainer>
  );
};

export default App;

```

#### Tab Navigation Ionicons

###### Configure Tab Nav


```javascript

import * as React from 'react';
import { View, StyleSheet, Text } from 'react-native';
import HomeScreen from './screens/HomeScreen';
import ProfileScreen from './screens/ProfileScreen';
import Ionicons from '@expo/vector-icons/Ionicons';
import { NavigationContainer } from '@react-navigation/native';
import { createBottomTabNavigator } from '@react-navigation/bottom-tabs';

const Tab = createBottomTabNavigator();

/**
 * The root component of the app, which sets up the navigation structure.
 * It uses a bottom tab navigator with two tabs: 'Home' and 'Profile'.
 */
export default function App() {
  return (
    <NavigationContainer>
      {/* Main container for the app */}
      <View style={styles.container}>
        {/* Bottom Tab Navigator */}
        <Tab.Navigator
          screenOptions={({ route }) => ({
            tabBarIcon: ({ size, color }) => {
              let iconName;

              // Define the icon name based on the current tab's route name
              if (route.name === 'Home') {
                iconName = 'home-outline';
              } else if (route.name === 'Profile') {
                iconName = 'person-outline';
              }

              // Return the Ionicons component with the specified name, size, and color
              return <Ionicons name={iconName} size={size} color={color} />;
            },
          })}
          tabBarOptions={{
            activeTintColor: 'tomato',
            inactiveTintColor: 'gray',
          }}>
          {/* Home Screen Tab */}
          <Tab.Screen name="Home" component={HomeScreen} />
          {/* Profile Screen Tab */}
          <Tab.Screen name="Profile" component={ProfileScreen} />
        </Tab.Navigator>
      </View>
    </NavigationContainer>
  );
}

// Styles for the components
const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#f0f0f0',
  },
});


```

#### Drawer Navigation


```javascript

import React from 'react';
import { NavigationContainer } from '@react-navigation/native';
import { createDrawerNavigator } from '@react-navigation/drawer';
import WelcomeScreen from './WelcomeScreen';
import MenuScreen from './MenuScreen';

const Drawer = createDrawerNavigator();

export default function App() {
  return (
    <NavigationContainer>
      <Drawer.Navigator
        useLegacyImplementation
        screenOptions={{ drawerPosition: 'right' }}>
        <Drawer.Screen name="Home" component={HomeScreen} />
        <Drawer.Screen name="Settings" component={SettingsScreen} />
        <Drawer.Screen name="Profile" component={ProfileScreen} />
        <Drawer.Screen name="Favorites" component={FavoritesScreen} />
        <Drawer.Screen name="About" component={AboutScreen} />
        <Drawer.Screen name="Contact" component={ContactScreen} />
      </Drawer.Navigator>
    </NavigationContainer>
  );
}

```

#### 

###### 


```javascript

```








