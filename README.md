# react-redux-note #
* react js basic
* relative packages
* collections of example codes
* Source of learning react js

## Example ##

1. Javascript Event and Data Changes - From [LearnCode.academy](https://www.youtube.com/watch?v=_D1JGNidMr4&list=PLoYCgNOIyGABj2GQSlDRjgvXtqfDxKm5b&index=5)
  ```js
  // Layout.js
  export default class Layout extends React.Component{
    constructor() {
      super();
      this.state = {
        title:"welcome"
      };
      
    changeTitle(title) {
      this.setState({title});
    }
  
    render() {
      return (
        <div>
          <Header changeTitle={this.changeTitle.bind(this) title={this.state.title} />
        </div>
      );
    }
  }
  ```
  
  ```js
  //Header.js
  export default class Header extends React.Component {
    handlChange(e) {
      const title = e.target.value;
      this.props.changeTitle(title);
    }
    
    render() {
      return (
        <div>
          <Title title={this.props.title} />
          <input onChange={this.handleChange.bind(this)} />
        </div>
      );
    }
  }
  ```
  
  ```js
  //Title.js
  export default class Title extends React.Component {
    render() {
      return (
        <h1>{this.props.title}</h1>
      );
    }
  }
  ```
--
2. use Ajax/axios requests in React js - From [Brad Westfall](https://www.youtube.com/watch?v=A2-u0KnyxWs)
  ```js
  import React from 'react'
  import ReactDOM from 'react-dom'
  import axios from 'axios'

  let User = function(props) {
    return (
      <div className="user">
        <div>Name: {props.name}</div>
      </div>
    )
  }

  let App = React.createClass({

    getInitialState: function() {
      return {
        users: []
      }
    },
    // get request from website
    componentDidMount: function() {
      axios.get('http://swapi.co/api/people').then(results => {
        this.setState({
          users: results.data.results
        })
      })
    },
    // use map to loop through all the data
    render: function() {
      return (
        <div>
          <h1>Star Wars Characters:</h1>
          {this.state.users.map(user => {
            return <User name={user.name} key={user.name} />
          })}
        </div>
      )
    }
  })

  ReactDOM.render(<App />, document.getElementById('root'))
  ```
--
3. Basic redux store and reducer codes - From [LearnCode.academy](https://www.youtube.com/watch?v=ucd5x3Ka3gw&index=17&list=PLoYCgNOIyGABj2GQSlDRjgvXtqfDxKm5b)
  ```js
  import { createStore } from "redux";
  const reducer = function (state, action) {
    if (action.type ==="INC") {
      return state+action.payload;
    }
    if (action.type ==="DEC") {
      return state-action.payload;
    }
    return state;
  }
  
  const store = createStore(reducer, 0);
  store.subscrbe(() => {
    console.log("store changed", store.getState())
  })
  
  store.dispatch({type: "INC", payload: {1}})
  store.dispatch({type: "INC", payload: {1}})
  //output: 
  //store changed 1
  //store changed 3
  ```
--
4. connect react and redux, get data from website use axios in action files. - From [learnCode.academy](https://www.youtube.com/watch?v=nrg7zhgJd4w&index=21&list=PLoYCgNOIyGABj2GQSlDRjgvXtqfDxKm5b)

  * [source codes](https://github.com/learncodeacademy/react-js-tutorials/tree/master/5-redux-react)
  
  --
  
5. continue..

  
