## Single Page Application

### Users expect app in browser to do the right thing
- Navigate with forward and back buttons,
browser page history
- Navigate away and come back to the app
- Bookmark a place in the app
- Copy the URL from the location bar and share it with someone
- Push the page refresh button on the browser

### Changing URL without page refresh
- Can change hash fragment in URL without reload
```
http://example.com
http://example.com#fragment
http://example.com?id=3535
http://example.com?id=3535#fragment
```
- HTML5 give JavaScript control of page reload
  - Browser History API - window.history - Change URL without reloading page

### Deep linking
- Concept: the URL should capture the web app's context so that directing the
browser to the URL will result the app's execution to that context
  - Bookmarks
  - Sharing

- Context is defined by the user interface designer!

### Deep linking in Single Page Apps
Two approaches:
- Maintain the app's context state in the URL
  - Works for browser navigation and refresh
  - User can copy URL from location bar
- Provide a share button to generate deep linking URL
  - Allows user to explicitly fetch a URL
  based on need
  - Can keep URL in location bar pretty

Either way web app needs to be able to initialize self from deep linked URL

### ReactJS support for SPA
- ReactJS has no opinion! Need 3rd party module.
- Example: React Router https://reacttraining.com/react-router/
  - Idea: Use URL to control conditional rendering
- Various ways of encoding information in URL
  - In fragment part of the URL: HashRouter
  - Use HTML5 URL handler: BrowserRouter
- Import as a module:
```js
import {HashRouter, Route, Link, Redirect} from 'react-router-dom';
```

### Example React Router 
```jsx
<HashRouter>
  <div>
    ...
    <Route path='/states' compont={States} />
    ...
    <Link to='/states'>States</Link>
    ... 
  </div>
</HashRouter>
```
- JSX block controlled by URL enclosed in HashRouter
- Route will render the component if URL matches.
- Use Link component to generated hyperlink:
```html
<a href="#/states">
 States
</a>
```

### Passing parameters with React Router
- Parameter passing in URL
```jsx
<Route
 path="/Book/:book/ch/:chapter"
 component={BookChapterComponent}
/>
```
- Parameters put in prop.match of the component 
```jsx
function BookChapterComponent({ match }) {
  return ( 
    <div>
      <h3>Book: {match.params.book}</h3>
      <h3>Chapter: {match.params.chapter}</h3>
    </div> 
  );
}
```

### Route: component=, render=, children=
- `component={BookChapterComponent}`
  - Mounts components on match (unmounts on URL change)
  - Passes match object with: `params`, `url`, `history`
- `render={props => <BookChapterComponent book={props.match.params.book} chapter={props.match.params.chapter} />}`
  - Calls function with props having match object from above.
  - Doesn't mount/unmount component (does update it)
- children= - Like render= except is called regardless of the match
  - match will be null if URL doesn't match
  - Useful if you want to have something always render but only active on matching URL.

Multiple route matches have precedence order: component, render, children
  - Switch is useful with multiple Route - Renders the first matching one