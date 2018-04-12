# Crashcourse React

## Presentation



## Demo

#### Libraries to Include
- React
- React DOM
- Babel (for converting JSX to JS)


#### Libraries to Include
- React
- React DOM
- Babel (for confverting JSX to JS)
- icomoon



#### Part 1 - Basic Syntax
```js

/*
 * A simple React component
 */
class Application extends React.Component {
  render() {
    return <div>
      <header>
        <h1>Product List</h1>
        <p>Everything you could possibly want</p>
      </header>

      <hr/>
  }
}

// ....

/*
 * Render the above component into the div#app
 */

ReactDOM.render(<Application />, document.getElementById('app'));

```


#### Part 2 - Props
```js

/*
 * A simple React component
 */
class Application extends React.Component {
  render() {
    return <div>
      {/* ... */ }

      <Product/>
  }
}

class Product extends React.Component{
  render(){
    return <article>

      <i className={this.props.iconName} style={{color: 'this.state.itemColo'r}} />
      <h3>{this.props.name}</h3>
      <h5>${this.props.price}</h5>

      <h4>Select Color</h4>
       <button
        onClick={()=>this._handleClick("dimgray")}
        style={{background: 'dimgray'}}/>
      <button
        onClick={()=>this._handleClick("darkred")}
        style={{background: 'darkred'}}/>
      <button
        onClick={()=>this._handleClick("darkblue")}
        style={{background: 'darkblue'}}/>
      <button
        onClick={()=>this._handleClick("darkgreen")}
        style={{background: 'darkgreen'}}/>

      </aside>
    </article>
  }
}



// ....

/*
 * Render the above component into the div#app
 */

//....

```


#### Part 3 - State
```js

/*
 * A simple React component
 */
class Application extends React.Component {
  render() {
    return <div>
      {/* ... */ }

      <Product/>
  }
}

class Product extends React.Component{
 // +++ ADD THIS +++
  constructor(props){
    super(props)
    this.state = {
      itemColor: 'dimgray'
    }
  }

  _handleClick (val){
    this.setState({itemColor: val})
  }

  render(){


    return <article>

      <i className={this.props.iconName}
      // +++ ADD THIS ++++
     style={{color: this.state.itemColor}} />
      <h3>{this.props.name}</h3>
      <h5>${this.props.price}</h5>

      <h4>Select Color</h4>
       <button
        onClick={()=>this._handleClick("dimgray")}
        style={{background: 'dimgray'}}/>
      <button
        onClick={()=>this._handleClick("darkred")}
        style={{background: 'darkred'}}/>
      <button
        onClick={()=>this._handleClick("darkblue")}
        style={{background: 'darkblue'}}/>
      <button
        onClick={()=>this._handleClick("darkgreen")}
        style={{background: 'darkgreen'}}/>

      </aside>
    </article>
  }
}
```

#### Fin
```js

let productsList = [
  {name: 'Slice of Pizza', iconName: 'ion-pizza', price: 7},
  {name: 'Wrench', iconName: 'ion-wrench', price: 6},
  {name: 'Pencil', iconName: 'ion-edit', price: 4},
  {name: 'Paper Airplane', iconName: 'ion-paper-airplane', price: 2},
  {name: 'T-shirts', iconName: 'ion-tshirt', price: 25},
  {name: 'Celtic Warhorn', iconName: 'ion-speakerphone', price: 95},
]

/*
 * A simple React component
 */
class Application extends React.Component {
  render() {
    return <div>
      <header>
        <h1>Product List</h1>
        <p>Everything you could possibly want</p>
      </header>

      <hr/>

      {/* <Product name={'Hammer'} iconName={'ion-hammer'} price={6} />*/}

      {
        productsList
          .map( product => {
            return <Product
                     name={product.name}
                     iconName={product.iconName}
                     price={product.price}
         /> })
      }
    </div>
  }
}

class Product extends React.Component{
  constructor(props){
    super(props)
    this.state = {
      itemColor: 'dimgray'
    }
  }

  _handleClick (val){
    this.setState({itemColor: val})
  }

  render(){
    return <article>

      <i className={this.props.iconName} style={{color: this.state.itemColor}} />
      <h3>{this.props.name}</h3>
      <h5>${this.props.price}</h5>

      <h4>Select Color</h4>

      <aside>
         {
           ['rebeccapurple', 'papayawhip', 'peru', 'cornflowerblue', 'indianred'].map( theColor => <button
                                style={{ background : theColor}}
                                onClick={()=> this._handleClick(theColor) }
                                                     />                                                                                              )
         }
        {/*
         <button
          onClick={()=>this._handleClick("dimgray")}
          style={{background: 'dimgray'}}/>
        <button
          onClick={()=>this._handleClick("darkred")}
          style={{background: 'darkred'}}/>
        <button
          onClick={()=>this._handleClick("darkblue")}
          style={{background: 'darkblue'}}/>
        <button
          onClick={()=>this._handleClick("darkgreen")}
          style={{background: 'darkgreen'}}/>
        */
        }
      </aside>
    </article>
  }
}



/*
 * Render the above component into the div#app
 */

ReactDOM.render(<Application />, document.getElementById('app'));
```
