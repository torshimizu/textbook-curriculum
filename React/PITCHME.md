@title[Introduction]

# Ada React Curriculum

#### Overview and Introduction to React.js

---
### Agenda
<ul>
  <li>What is React?</li>
  <li>Why React?</li>
  <li>React Hello World</li>
  <li>Components</li>
  <li>props & state</li>
  <li>Curriculum Overview
    <ul>
      <li>Week 1</li>
      <li>Week 2</li>
      <li>Week 3</li>
    </ul>
  </li>
<ul>

---

@title[PITCHME.md]

### What is React?
<ul>
  <li>Open source library for building user interfaces</li>
</ul>

---
### Why React?
#### Industry Relevant

<ul>
  <li>Many organizations are using React to create zippy web interfaces</li>
  <li>Relevant and recent documentation with a large support community</li>
  <li>Article: <a href="https://medium.com/netflix-techblog/netflix-likes-react-509675426db">Netflix likes React</a></li>
  <li>Article: <a href="https://medium.com/@coderacademy/32-sites-built-with-reactjs-172e3a4bed81">32 Sites Built with React</a></li>
</ul>
---

### Why React?
#### Virtual DOM

<ul>
  <li>Every DOM object has a copy</li>
  <li>React does a diff between DOM and Virtual DOM and updates only the objects that have changed in the DOM</li>
</ul>
<span><a href="https://www.codecademy.com/articles/react-virtual-dom">Virtual DOM on CodeCademy</a></span>

---

### React Hello World

```shell
npm install -g create-react-app
create-react-app react-practice
cd react-practice
```

@[1](Install the package that will set up npm and all necessary dependencies)
@[2](Create a new react app called `react-practice`)
@[3](Move into the folder created and open in text-editor)
---

### React Hello World

By default we get an application that can be run using `npm start`.

Give it a try!

---

### File Structure

- `index.js` is the React file created automatically (not a component)
- `app.js` is the outermost React component

---
### `index.js`

```javascript
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
import App from './App';
import registerServiceWorker from './registerServiceWorker';

ReactDOM.render(<App />, document.getElementById('root'));
registerServiceWorker();

```

@[1-5](Default import statements)
@[7](Render a single React component called `App` and add it to the DOM at HTML element "root")
---

### `index.js`

Interestingly enough, we don't modify HTML files in a React application. We can find that initial "root" element in the file at `public/index.html`, though we won't really need to use the `index.html` file much more than that.
---

### `app.js`

```javascript
import React, { Component } from 'react';
import logo from './logo.svg';
import './App.css';

class App extends Component {
  render() {
    return (
      <div className="App">
        <header className="App-header">
          <img src={logo} className="App-logo" alt="logo" />
          <h1 className="App-title">Welcome to React</h1>
        </header>
        <p className="App-intro">
          To get started, edit <code>src/App.js</code> and save to reload.
        </p>
      </div>
    );
  }
}

export default App;
```

@[1-3](Import React components and automatic dependencies)
@[5](Name and create a component)
@[6-18](Define the `render` function which will determine what JSX elements to display in the DOM)

---

### Curriculum Overview: Week 1

**Lectures**
- Intro to React
- Hello World
- Creating Components
- props & state
- Firebase & basic lifecycle methods
- Forms

---

### Curriculum Overview: Week 1

**Project**

TREaKt

Based off the existing BackTREK project.

**Learning Goals:**
- Use React Components to structure an application
- Utilize state and props to manage data passing in and out of components
- Utilize events within the React construct
- Use firebase to manage data storage along with component lifecycle methods

**Functionality:**
- Read from firebase: list and details
- Create data in firebase

---

### Curriculum Overview: Week 2

**Lectures**
- Component Design
- More with Lifecycle Methods
- Testing

---


### Curriculum Overview: Week 2

**Project**
Ada Trader

**Learning Goals:**
- Create nested component structures that require nested event structures
- Manage data within state and props utilizing component design patterns

**Functionality:**
- List items
- Link components together with one another - passing data (and events) from one another
- Integrate with some existing code that we provide

---
