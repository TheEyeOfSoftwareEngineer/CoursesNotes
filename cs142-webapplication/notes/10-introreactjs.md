## Introduction to React.js

### React.js
- JavaScript framework for writing the web applications
  - Like AngularJS - Snappy response from
  running in browser
  - Less opinionated: only specifies
  rendering view and handling user
  interactions

- Uses Model-View-Controller pattern
  - View constructed from Components using pattern
  - Optional, but commonly used HTML templating

- Minimal server-side support dictated

- Focus on supporting for programming in the large and single page applications
  - Modules, reusable components, testing, etc.

### ReactJS tool chain
- Babel: Transpile language features (e.g. ECMAScript, JSX) to basic JavaScript

- Webpack: Bundle modules and resources (CSS, images)

Output loadable with single script tag in any browser

### Component state and input handling

```js
import React from 'react';
class ReactView extends React.Component {
  construtor(props) {
    super(props);
    this.state = {yourname: ""};
  }
  handleChange(event) {
    this.setState({yourname: event.target.value});
  }
}
```

Input calls to setState which causes React to call render() again

### One way binding: Type 'D' Character in input box 

```jsx
<input type="text" value={this.state.yourname} onChange={(event) => this.handleChange(event)} />
```

Triggers handleChange call with event.target.value == "D"
