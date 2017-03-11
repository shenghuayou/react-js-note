# react-js-note #
* react js basic
* Example codes in react js
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
