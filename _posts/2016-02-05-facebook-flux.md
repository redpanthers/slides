---
layout: slide
title: Facebook Flux
description:
theme: black
transition: slide
permalink: /facebook-flux
author: Sibin Xavier  
post_thumbnail:
profile_image:
---
<section data-markdown>
 Flux
</section>
<section>
	<h4>Sibin Xavier</h4>
	<p>
		Frontend Developer
	</p>
</section>
<section data-markdown>
  ## What is Flux
  * Flux is an architecture used at Facebook with React
  * Enhance React's features
  * It is an architecture not a library like
  Angular/ Backbone
  * Flux has Unidirectional data flow
</section>
<section data-markdown>
  ### Uni directional data flow
  * One directional data flow
  * More predictable nature
</section>
<section data-markdown>
  #### Example of Bi-directional data flow
  ![Bi-Directional]({{site.baseurl}}/assets/images/backbone-bi-directional.png)
</section>
<section data-markdown>
  #### Unidirectional data flow
  ![Uni directional data flow]({{site.baseurl}}/assets/images/uni-directional-data-flow.png)
</section>
<section data-markdown>
  ### Flux - Important points
  * Action
  * dispatcher
  * Store
</section>

<section data-markdown>
  #### Flux Architecture diagram
  ![Flux Architecture diagram]({{site.baseurl}}/assets/images/flux-simple-f8-diagram-explained.png)
</section>
<section data-markdown>
  #### Action
  * Collection of methods, that are called inside views
  * Action methods can used with javascript events like click, change, mouseleave etc
  * Action connected to dispatcher
</section>
<section data-markdown>
  ##### Example code for action
  ```
    import dispatcher from "../dispatcher";
    import constants from "../const/store-const";
    var checkoutActions = {
      addCart: function(data){
        dispatcher.dispatch({
          actionType: constants.ADD_CART,
          data: data
        })
      }
    }
    export default checkoutActions;
  ```
</section>
<section data-markdown>
  #### Dispatcher
  * Center hub for your application
  * Controls stores
  * Receive data from actions and trigger stores
</section>
<section data-markdown>
  ##### Example code Dispatcher
  ```
    import {Dispatcher} from 'flux';
    var dispatcher = new Dispatcher();
    export default dispatcher;
  ```
</section>
<section data-markdown>
  #### Dispatcher have
  * register (method)
  * unregister (string)
  * dispatch (object)
  * waitFor
  * isDispatching ( boolean)
</section>
<section data-markdown>
  ##### waitFor is not to handle ajax
  waitFor is used to wait some other store to complete it can't be used to make ajax calls
</section>
<section data-markdown>
  ```
    CountryStore.dispatchToken = flightDispatcher.register(function(payload) {
     if (payload.actionType === 'country-update') {
       CountryStore.country = payload.selectedCountry;
     }
    });
  ```
</section>
<section data-markdown>
  ```
  CityStore.dispatchToken = flightDispatcher.register(function(payload) {
  if (payload.actionType === 'country-update') {
    // `CountryStore.country` may not be updated.
    flightDispatcher.waitFor([CountryStore.dispatchToken]);
    // `CountryStore.country` is now guaranteed to be updated.

    // Select the default city for the new country
    CityStore.city = getDefaultCityForCountry(CountryStore.country);
  }
  });
  ```
</section>
<section data-markdown>
  #### Store
  * Manage application state
  * Use it to get initial data and updated data
</section>
<section data-markdown>
  ```
    import dispatcher from '../dispatcher.js';
    import EventEmitter from 'events';
    import assign from 'object-assign';
    var CHANGE_EVENT = 'change';
    var EventEmitterEvent  = EventEmitter.EventEmitter

    var _number  = 0;
    var checkoutStore = assign({}, EventEmitterEvent.prototype, {
      addCart: function(number){
        return _number = _number + number;
      },
      getCart: function(){
        return _number;
      },
      emitChange: function(){
        this.emit(CHANGE_EVENT)
      },
      addListener: function(callback){
        this.on(CHANGE_EVENT, callback)
      },
      removeListner: function(callback){
        this.removeListner(CHANGE_EVENT, callback)
      }
    });

    dispatcher.register((action)=>{
      switch (action.actionType){
        case 'ADD_CART':
          console.log("hello")
          checkoutStore.addCart(action.data)
          checkoutStore.emitChange()
          break;
      }
    })


    export default checkoutStore;
  ```
</section>
<section data-markdown>
  #### Event Emitter
  * Flux use similar node js Event emitter
  * EventEmitter listen/broadcast named events
</section>
<section data-markdown>
  #### Event emitter

  * emitter.on('event_name',callback) // addListener
  * emitter.emit('event_name')
  * emitter.removeListener('event_name')

</section>
<section data-markdown>
  ![Event Diagram]({{site.baseurl}}/assets/images/events.png)
</section>

<section data-markdown>
  #### React View and Flux

  * We can connect react components with react

</section>
<section data-markdown>
  ```
  class CartIconOnTopBar extends React.Component{
    constructor(){
      super()
      this.state = {
        cartItemCount: checkoutStore.getCart()
      }
    }
    componentDidMount(){
     checkoutStore.addListener(this.updateCart)
    };
    updateCart = () => {
      this.setState({
        cartItemCount: checkoutStore.getCart()
      })
    };
    openClassModal = () => {

    };
    render(){
      return(
          <li>
            <a href="#" onClick={this.openCartModal} className="cart-element">
              <i className="fi-shopping-cart"></i>
              <span className="cart-count"> {this.state.cartItemCount} </span>  
            </a>
          </li>
      )
    }
  }
    export default TopSearch;
  ```
</section>
<section data-markdown>
    ##### Reference
    - [NodeJS Events](https://nodejs.org/api/events.html)
    - [Flux Docs](http://facebook.github.io/flux/docs/overview.html#content)
    - [Scotch - Getting Know Flux](https://scotch.io/tutorials/getting-to-know-flux-the-react-js-architecture)
    - [Unidirectional data flow](https://medium.com/@AdamRNeary/unidirectional-data-flow-yes-flux-i-am-not-so-sure-b4acf988196c#.5olj6qx6k)    

</section>
