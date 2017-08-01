# React-Native-Snippets
### 1. Solving "Loading Roboto Font" error with Expor and Native-base 


```
export default class App extends React.Component { 

 state = {
        fontLoaded: false,
    };
      async componentWillMount() {
        await Expo.Font.loadAsync({
            'Roboto_medium': require('native-base/Fonts/Roboto_medium.ttf'),
            'Roboto': require('native-base/Fonts/Roboto.ttf')
        });
        
        this.setState({ fontLoaded: true });
    }
    
    render () {     
      return ( 
        this.state.fontloaded ? ( 
          <Text> This is a Test </Text>
        ) : null    
      );    
    }
}
