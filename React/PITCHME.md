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
  <li>Curriculum Overview<li>
  <ul>
    <li>Week 1</li>
    <li>Week 2</li>
    <li>Week 3</li>
  </ul>
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

By default we get an application that can be run using `npm start`. Give it a try!

---

### File Structure

- `index.js` is the React file created automatically (not a component)
- `app.js` is the outermost React component

---

### `app.js` code

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
@[6-15](Define the `render` function which will determine what JSX elements to display in the DOM)

---

#### No more <span class="gray">Keynote</span>.
#### No more <span class="gray">Powerpoint</span>.
<br>
#### Just <span class="gold">Markdown</span>.
#### Then <span class="gold">Git-Commit</span>.

---?code=assets/md/hello.md&title=Step 1. PITCHME.md

<br>
#### Create slideshow content using GitHub Flavored Markdown in your favorite editor.

<span class="aside">It's as easy as README.md with simple slide-delimeters (---)</span>

---

@title[Step 2. Git-Commit]

### <span class="gold">STEP 2. GIT-COMMIT</span>
<br>

```shell
$ git add PITCHME.md
$ git commit -m "New slideshow content."
$ git push

Done!
```

@[1](Add your PITCHME.md slideshow content file.)
@[2](Commit PITCHME.md to your local repo.)
@[3](Push PITCHME.md to your public repo and you're done!)
@[5](Supports GitHub, GitLab, Bitbucket, GitBucket, Gitea, and Gogs.)

---

@title[Step 3. Done!]

### <span class="gold">STEP 3. GET THE WORD OUT!</span>
<br>
![GitPitch Slideshow URLs](assets/images/gp-slideshow-urls.png)
<br>
<br>
#### Instantly use your GitPitch slideshow URL to promote, pitch or present absolutely anything.
