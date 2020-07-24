# Configure_Reactotron_ReactJS_Poject

1 - Init with Reactotron in project React JS (Using Redux):
	
	yarn add reactotron-react-js reactotron-redux
  
 2 - Create folder config
 
 3 - Create file ReactotronConfig.js inside config folder
	
  4 - ReactotronConfig file:
    
    import Reactotron from 'reactotron-react-js';

    import { reactotronRedux } from 'reactotron-redux';

    if (process.env.NODE_ENV === 'development') {
      const tron = Reactotron.configure().use(reactotronRedux()).connect();

      tron.clear();

      console.tron = tron;
    }

   5 - Redux file store configure:
    - Adding line:
      
      const enhancer = process.env.NODE_ENV === 'development' ? console.tron.createEnhancer() : null;
      
      const store = createStore(rootReducer, enhancer);
      
   6 - Import ReactotronConfig in App.js or App.ts file:
        
        import './config/ReactotronConfig';
