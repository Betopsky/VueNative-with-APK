<template>  
  <app-navigator>

  </app-navigator>
</template>

<script>
import {
  createAppContainer,
  createMaterialTopTabNavigator,
  createBottomTabNavigator,
  createStackNavigator
} from "vue-native-router";

import CameraScreen from "./screens/Camera.vue";
import HomeScreen from "./screens/Home.vue";
import WebServiceScreen from "./screens/WebService.vue";


//import ImageBrowserScreen from "./screens/ImageBrowser.vue";


const Tabs = createMaterialTopTabNavigator({
  Camera: HomeScreen,
  API: WebServiceScreen,
  // API2: ImageBrowserScreen,
});

const StackNavigator = createStackNavigator(
  {
    Tabs,
    Camara: CameraScreen
  },
  {
    defaultNavigationOptions: {
      gestureEnabled: false,
      title: "Fotos & Video",
      headerTitleStyle: {
        textAlign: "center",
        alignSelf: "center",
        color: "white"
      },
      headerStyle: {
        backgroundColor: "black"
      }
    }
  }
);

const AppNavigator = createAppContainer(StackNavigator);

export default {
  components: { AppNavigator }
};
</script>

<style>  
#app {    
  font-family: 'Avenir', Helvetica, Arial, sans-serif;    
  -webkit-font-smoothing: antialiased;    
  -moz-osx-font-smoothing: grayscale;    
  text-align: center;    
  color: #2c3e50;    
  margin-top: 60px;  
}  
</style>