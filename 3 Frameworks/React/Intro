


# React

## loading boilerplate

```
npx create-react-app my-app
cd my-app
npm start
```
### create a component

start in the src folder, leave only index.js and index.css
copy these lines at the start of the index.js file.

    import React from 'react';
    import ReactDOM from 'react-dom';
    import './index.css';

   - you need to extend React.Component
   - note that only one div is allowed

    class Component extends React.Component {
	    render(){
	    	return(
				<div> content </div>
			);
	    }
	 }

- render the component in the main render

      ReactDOM.render(
      <Component />,
      document.getElementById('root'));
    
## JSX Syntax

React.createElement('div'); instead of <div>

```
return React.createElement('div', {className: 'shopping-list'},
  React.createElement('h1', /* ... h1 children ... */),
  React.createElement('ul', /* ... ul children ... */)
);
```

### Template for a new component

    import React, { Component } from 'react';
    
    class TodoItems extends Component {
        render(){
        	return(
    			<div> content </div>
    		);
        }
     }
    
    export default TodoItems;

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTI0NzYwNTY4NywtMTU2ODI0Njk4NSw5ND
Y0NTMxNywtMTk5NDc2MTAyNSwyMDQwMjk3NjIyXX0=
-->