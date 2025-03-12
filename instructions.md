# Setup a ReactJS Development Environment

# # Why React?

• Solves the problem of redundancy in html
• A non-laggy user experience.
• React Native is similar so it’s an easy transition to mobile development.

# Download Node and NPM

• nodejs.org

# Download Text Editor if you don’t have one

• Recommend Cursor
• cursor.com

# Create base project

## In terminal

• npx create-react-app [name of project]
• npm install react-router-dom
• npm run start

# Wrap application file with BrowserRouter

## index.js

import React from 'react';
import ReactDOM from 'react-dom/client';
import { BrowserRouter } from 'react-router-dom';
import App from './App';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
<BrowserRouter>
<App />
</BrowserRouter>
);

# Create components folder

## Create three page components (Home, About, Contact)

function Home() {
return (
<>

<h1>Home</h1>
<p>Welcome to the Home page!</p>
</>
);
}
export default Home;

# Create routes.js

import './App.css';
import { Routes, Route } from 'react-router-dom';
import Home from './components/Home';
import About from './components/About';
import Contact from './components/Contact';

function MainRoutes() {
return (
<Routes>
<Route path='/' element={<Home />} />
<Route path='/about' element={<About />} />
<Route path='/contact' element={<Contact />} />
</Routes>
);
}
export default MainRoutes;

# Add route and link files to App.js

import logo from './logo.svg';
import './App.css';
import { Link } from 'react-router-dom';
import MainRoutes from './routes';

function App() {
return (

<div className='App'>
<header className='App-header'>
<img src={logo} className='App-logo' alt='logo' />
<p>
Edit <code>src/App.js</code> and save to reload.
</p>
<a
          className='App-link'
          href='https://reactjs.org'
          target='_blank'
          rel='noopener noreferrer'
        >
Learn React
</a>
<Link to='/'>Home</Link>
<Link to='/about'>About</Link>
<Link to='/contact'>Contact</Link>
<MainRoutes />
</header>
</div>
);
}
export default App;

# Create Hello World component

• Different export form
• Don’t need the JSX fragment with just one element.
• Add to a page component

export default function HelloWorld({ name = 'World' }) {
return (
<>

<h1>Hello {name}</h1>
</>
);
}

# Create Namer component

• Add to other component.

import { useState } from 'react';

export default function Namer() {
const [name, setName] = useState('World');

return (
<>

<h3>My name is: {name}</h3>
<input value={name} onChange={(e) => setName(e.target.value)} />
<h1>Hello {name}!!!</h1>
</>
);
}
