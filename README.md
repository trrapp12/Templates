# Templates

resource for different code templates

### HTML template

*this boiler plate was provided by Louis Lazaris at [HTML5 Template: A Basic Boilerplate for Any Project](https://www.sitepoint.com/a-basic-html5-template/)*

```html
<!doctype html>

<html lang="en">
<head>
  <meta charset="utf-8">
  <!--set initial-scale=1 for a 1:1 aspect raito-->
  <meta name="viewport" content="width=device-width, initial-scale=1">

  <title>A Basic HTML5 Template</title>
  <meta name="description" content="A simple HTML5 Template for new projects.">
  <meta name="author" content="SitePoint">

  <meta property="og:title" content="A Basic HTML5 Template">
  <meta property="og:type" content="website">
  <meta property="og:url" content="https://www.sitepoint.com/a-basic-html5-template/">
  <meta property="og:description" content="A simple HTML5 Template for new projects.">
  <meta property="og:image" content="image.png">
  
  <!--favicon.ico is for older browsers-->
  <link rel="icon" href="/favicon.ico">
  <!--favicon.svg is for newer browsers-->
  <link rel="icon" href="/favicon.svg" type="image/svg+xml">
  <link rel="apple-touch-icon" href="/apple-touch-icon.png">
  
  <!--add multiple stylesheets if needed, last one to load will have higher priority for any conflicts-->
  <link rel="stylesheet" href="css/styles.css?v=1.0">

</head>

<body>
  <!-- your content here... -->
  <script src="js/scripts.js"></script>
</body>
</html>

```

# CSS

<details>
  <summary>Selectors</summary>
  
  | selectors    | example    | description             | combinators         | example       | description                                              |
|--------------|------------|-------------------------|---------------------|---------------|----------------------------------------------------------|
| element      | p { }      | selects element         | element element     | div p { }     | selects all p elements inside div elements               |
| id           | #id { }    | selects by id           | element > element   | div > p { }   | selects all p elements where the parent is a div element |
| class        | .class { } | selects by class        | element.class       | div.class { } | selects all elements with a class of "class"             |
| attribute    | img[src]   | selects by attribute    | element + element   | div + p       | selects the first p element after a div                  |
| Pseudo-class | a: hover   | selects by pseudo-class | element1 ~ element2 | div ~ p       | selects every p element preceeded by a div               |
| *            | misc       | selects all elements    | element,element     | div, p        | selects all div elements and all p elements              |
|              |            |                         |                     |               |                                                          |
|              |            |                         |                     |               |                                                          |

*for a comprehensive list of selectors see [w3schools CSS Selector Reference](https://www.w3schools.com/cssref/css_selectors.asp)*
  
</details>

<details>
  <summary>Specificity</summary>
  
*this example taken from [Chris Coyier's](https://css-tricks.com/author/chriscoyier/) article [Specifics on CSS Specificity](https://css-tricks.com/specifics-on-css-specificity/)*

![specificity-calculationbase_rhrovi](https://user-images.githubusercontent.com/11747875/141937727-07286bb4-1909-4913-ab47-57a7c28e6f8f.png)
  
</details>


<details>
  <summary>Simple Grid Layout in CSS Grid</summary>
  
  ```html
<style>
  .item1{background:LightSkyBlue;}
  .item2{background:LightSalmon;}
  .item3{background:PaleTurquoise;}
  .item4{background:LightPink;}
  .item5{background:PaleGreen;}
  .item6{background:Yellow;}

  .container {
    font-size: 40px;
    min-height: 300px;
    width: 100%;
    background: LightGray;
    display: grid;
  /*this sets fractional relationship a column takes.  For example, 1 fr 2fr 1fr would mean the center column is twice as wide as the side columns. */
    grid-template-columns: 1fr 1fr 1fr;
  /*this sets fractional relationship a row takes.  For example, 1 fr 2fr 1fr would mean the center column is twice as wide as the side rows. */
    grid-template-rows: 1fr 1fr 1fr;
  /*this sets the gap between the columns */
    grid-gap: 10px;
  /*this defines the order of the template area.  Note, having the same name repeat vertically or horizontally shows it spans the entire area  */
    grid-template-areas:
      "header header header"
      "content content content"
      "footer footer footer";
  }
</style>

<div class="container">
  <div class="item1">1</div>
  <div class="item2">2</div>
  <div class="item3">3</div>
  <div class="item4">4</div>
  <div class="item5">5</div>
  <div class="item6">6</div>
</div>
```

</details>

# JavaScript 


### falsy values
| Falsy Values | Definitions     |
|--------------|-----------------|
| false        | false           |
| 0            | the number zero |
| ""           | empty string    |
| NaN          | There are five different types of operations that return NaN:  * Number cannot be parsed (e.g. parseInt("blabla") * Number(undefined)) * Math operation where the result is not a real number (e.g. Math.sqrt(-1)) * Operand of an argument is NaN (e.g. 7 ** NaN) Indeterminate form (e.g. 0 * Infinity, or undefined + undefined) * Any operation that involves a string and is not an addition operation (e.g. "foo" / 3) |
| undefined    | undefined is a property of the global object. That is, it is a variable in global scope. The initial value of undefined is the primitive value undefined. A variable that has not been assigned a value is of type undefined. A method or statement also returns undefined if the variable that is being evaluated does not have an assigned value. A function returns undefined if a value was not returned. |
| null         | The value null is written with a literal: null. null is not an identifier for a property of the global object, like undefined can be. Instead, null expresses a lack of identification, indicating that a variable points to no object. In APIs, null is often retrieved in a place where an object can be expected but no object is relevant. ||


### Escape Line characters
|Code          |      Output    |
|--------------|----------------|
| ``` \' ```	 | single quote   |
| ``` \" ```	 | double quote   |
| ``` \\ ```	 | backslash      |
| ``` \n ```	 | newline        |
| ``` \r	```  | carriage return|
| ``` \t	```  | tab            |
| ``` \b	```  | word boundary  |
|``` \f	```    | form feed      |

<details>
  <summary>Break Case Statement</summary>
  
```javascript

function caseInSwitch(val) {
  let answer = "";
  //notice val is getting evaluated, so put in (), then use {}
  switch(val) {
  //notice syntax is "case" + expected output + ":"
    case 1:
  //notice we set the variable to be returned to the value in the ""
      answer = "alpha"; 
  //must have break or will evaluate next statement
      break;
    case 2:
      answer = "beta"
      break;
    case 3:
      answer = "gamma"
      break;
    case 4:
      answer = "delta"
  //notice you can put a default response, like the last "else" of a "if/else" statement
    default
      answer = "answer not found"
  }

  return answer;
}

caseInSwitch(1);
  
```
  
</details>

<details>
  <summary>Break Case with multiple inputs triggering same output</summary>
  
```javascript

function sequentialSizes(val) {
  let answer = "";
  // Only change code below this line
  switch(val) {
  //notice it will evaluate 1, 2, or 3 and all will answer "Low" since no break statement separates them
    case 1:
    case 2: 
    case 3: 
      answer = "Low";
      break;
    case 4: 
    case 5: 
    case 6: 
      answer = "Mid";
      break; 
    case 7: 
    case 8: 
    case 9: 
      answer = "High";
      break;
  }


  // Only change code above this line
  return answer;
}

sequentialSizes(1);
  
```
  
</details>

<details>
  <summary>Short hand return boolean value function</summary>
  
  Sometimes people use an if/else statement to do a comparison, like this:

```javascript

function isEqual(a, b) {
  if (a === b) {
    return true;
  } else {
    return false;
  }
}

//But there's a better way to do this. Since === returns true or false, we can return the result of the comparison:

function isEqual(a, b) {
  return a === b;
}

```

</details>

<details>
  <summary>For Loop</summary>

```javascript

for (let i = 0; i < 5; i++) {
  ourArray.push(i);
}

```

</details>
  
<details>
  <summary>Nested for Loop</summary>

```javascript

for (let i = 0; i < arr.length; i++) {
  for (let j = 0; j < arr[i].length; j++) {
    console.log(arr[i][j]);
  }
}

```

</details>
  
  <details>
  <summary>Backwards For Loop</summary>

```javascript

for (let i = 10; i > 0; i--) {
  ourArray.push(i);
}

```

</details>
  
  <details>
  <summary>For Loops with Steps</summary>

```javascript

for (let i = 10; i > 0; i -= 2) {
  ourArray.push(i);
}

```

</details>
  
<details>
  <summary>Ternary Operators</summary>

```javascript

function findGreater(a, b) {
  return a > b ? "a is greater" : "b is greater or equal";
  // the statement before the '?' is what is being evaluated.  
  // What is between the '?' and the ':' is what is returned if it is true.  
  // What is to the right of the ':' is what is returned if it's not true.
}

```

</details>
  
<details>
  <summary>Multiple Ternary Operators</summary>

```javascript

function findGreaterOrEqual(a, b) {
  return (a === b) ? "a and b are equal" 
    : (a > b) ? "a is greater" 
    : "b is greater";
}

```

</details>
  
  <details>
  <summary>Rest Argument</summary>
    
    The rest argument is passed into the parameters to show that there may be a variation in the number of parameters that will be passed it.  It may be 1, or 2, or 35...
    The syntax would turn the first example (which can only receive 3 arguments) into the second (which can receive any number of arguments).

```javascript

const sum = (x, y, z) => {
  const args = [x, y, z];
  return args.reduce((a, b) => a + b, 0);
}

```
    
into 
    
```javascript
    
const sum = (...args) => args.reduce((a, b) => a + b, 0)
    
```
    

</details>
  
   <details>
  <summary>Spread Operator</summary>
    
  Unlike the rest parameter which "packs" things into an array, the spread operator "unpacks" an array.  So to use it you first have to have 
     
     1 - an iterable object (array, map, or set)
     2 - invoke the syntax

```javascript

const odd = [1,3,5];
//const odd is the iterable object
const combined = [2,4,6, ...odd];
//... says we want to unpack them, then we follow it with the variable name
console.log(combined);

```

output: 
    
```javascript
    
[ 2, 4, 6, 1, 3, 5 ]
    
```
    

</details>

# React


<details>
  <summary>Adding React to Development</summary>

  *this source comes from the [React Docs](https://reactjs.org/docs/add-react-to-a-website.html).*


```html 
<!--these first two scripts add the development version of react 
  <script src="https://unpkg.com/react@17/umd/react.development.js" crossorigin></script>
  <script src="https://unpkg.com/react-dom@17/umd/react-dom.development.js" crossorigin></script>

  <!-- replace the "like_button.js" with the file name of the JS file where your React is written. -->
  <script src="like_button.js"></script>
```
  
</details>


<details>
  <summary>Adding React to Production</summary>

  ```html
<!--add these scripts to the bottom of the page -->
<script src="https://unpkg.com/react@17/umd/react.production.min.js" crossorigin></script>
<script src="https://unpkg.com/react-dom@17/umd/react-dom.production.min.js" crossorigin></script>
```
  
</details>

<details>
  <summary>Adding React with JSX</summary>
  
```html
<!--add this script to the bottom of the page -->
<script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
```
  
</details>

<details>
  <summary>Pass an Array using Props</summary>

  ```javascript
  
const List = props => {
  //notice that when we define the variable we define the actions taken on it.  Also .tasks must match a tasks added when the element is rendered
  return <p>{props.tasks.join(", ")}</p>;
};

class ToDo extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return (
      <div>
        <h1>To Do Lists</h1>
        <h2>Today</h2>
        //notice the array is surrounded by {}
        <List tasks={["Walk", "Cook", "Bake"]} />
        <h2>Tomorrow</h2>
        <List tasks={["Study", "Code", "Eat"]} />
      </div>
    );
  }
}

```
  
</details>

<details>
  <summary>Create a Stateful Component</summary>

```javascript
class StatefulComponent extends React.Component {
  constructor(props) {
    super(props);
    //notice it's after props we set it.  We use this.state.  We set it equal to an object. In object we use key: value notation.
    this.state = {
      name: "Trevor"
    }

  }
  render() {
    return (
      <div>
        //notice we call it with this.state.name
        <h1>{this.state.name}</h1>
      </div>
    );
  }
};
```
</details>

<details>
  <summary>Pass State as Props to Child Component</summary>
  
```javascript
  
class MyApp extends React.Component {
  constructor(props) {
    super(props);
    //state is defined within constructor block, after super using "this.state" set equal to an object, then using key, value pairs
    this.state = {
      name: "CamperBot",
      customerId : 856849392
    };
  }
  render() {
    return (
      <div>
        // Here we give the Navbar a prop of name, and then call this.state.name, 
        //since we only need that, in order to pass the value of CamperBot to the NavBar component
        <Navbar name={this.state.name} />
      </div>
    );
  }
}

class Navbar extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return (
      <div>
        // Notice we don't use this.state.name.  We access it with this.props Since we passed in the CamperBot state value 
        //into the the NavBar component above the h1 element below will render the value passed from state
        <h1>Hello, my name is: {this.props.name}</h1>
      </div>
    );
  }
}
```
  
</details>

<details>
  <summary>Add Event Listeners</summary>
  
```javascript
  
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      message: ""
    };
    //create an event handler here to handle enter
    this.handleEnter = this.handleEnter.bind(this);
    //create an eventhandler here for keypress which binds "this"
    this.handleKeyPress = this.handleKeyPress.bind(this);
  }
  //componentDidMount() a good method to attach event listeners
  componentDidMount() {
    document.addEventListener("keydown", this.handleKeyPress);
  }
  //use this to clear eventlistener
  componentWillUnmount() {
    document.removeEventListener("keydown", this.handleKeyPress);
  }

  handleEnter() {
    this.setState({
      message: this.state.message + "You pressed the enter key! "
    });
  }
  handleKeyPress(event) {
    if (event.keyCode === 13) {
      this.handleEnter();
    }
  }
  render() {
    return (
      <div>
        <h1>{this.state.message}</h1>
      </div>
    );
  }
}
```
  
</details>

# ADA Considerations 

*taken from [MDN: CSS and JavaScript accessibility best practices](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript)*

<details>
  <summary>Abbreviation</summary>
  
  
```html

<p>Web content is marked up using <abbr title="Hypertext Markup Language">HTML</abbr>.</p>

```
  
  The recognized styling convention for abbreviations is a dotted underline, and it is unwise to significantly deviate from this. For more on abbreviations, 
  
</details>


<details>
  <summary>Emphasized Text</summary>
  
  ```html
<p>The water is <em>very hot</em>.</p>

<p>Water droplets collecting on surfaces is called <strong>condensation</strong>.</p>
```

</details>

<details>
  <summary>Links</summary>
  
```html

<p>Visit the <a href="https://www.mozilla.org">Mozilla homepage</a>.</p>

```
  
  The standard link conventions are underlined and a different color (default: blue) in their standard state, another color variation when the link has previously been visited (default: purple), and yet another color when the link is activated (default: red). In addition, the mouse pointer changes to a pointer icon when links are moused over, and the link receives a highlight when focused (e.g. via tabbing) or activated. The following image shows the highlight in both Firefox (a dotted outline) and Chrome (a blue outline):


You can be creative with link styles, as long as you keep giving users feedback when they interact with the links. Something should definitely happen when states change, and you shouldn't get rid of the pointer cursor or the outline — both are very important accessibility aids for those using keyboard controls.

### Hiding content

There are many instances where a visual design will require that not all content is shown at once. For example, in our Tabbed info box example (see source code) we have three panels of information, but we are positioning them on top of one another and providing tabs that can be clicked to show each one (it is also keyboard accessible — you can alternatively use Tab and Enter/Return to select them).


Screen reader users don't care about any of this — they are happy with the content as long as the source order makes sense, and they can get to it all. Absolute positioning (as used in this example) is generally seen as one of the best mechanisms of hiding content for visual effect, because it doesn't stop screen readers from getting to it.

On the other hand, you shouldn't use visibility:hidden or display:none, because they do hide content from screen readers. Unless of course, there is a good reason why you want this content to be hidden from screen readers.

</details>


<details>
  <summary>Accessibility Checklist</summary>
  
  *from [ADA Best Practices Tool Kit for State and Local Governments, Chapter 5 Addendum: Title II Checklist](https://www.ada.gov/pcatoolkit/chap5chklist.htm)
  
- [x] Does the top of each page with navigation links have a “skip navigation” link? (This feature directs screen readers to bypass the row of navigation links and start at the webpage content, thus enabling people who use screen readers to avoid having to listen to all the links each time they move to a new page.)

- [x] Do all links have a text description that can be read by a screen reader (not just a graphic or “click here”)?

- [x] Do all of the photographs, maps, graphics and other images on the website currently have HTML tags (such as an “alt” tag or a long description tag) with text equivalents of the material being visually conveyed?

- [x] Are all of the documents posted on your website available in HTML or another text-based format (for example, rich text format (RTF) or word processing format), even if you are also providing them in another format, such as Portable Document Format (PDF)?

- [x]  If your website has online forms, do HTML tags describe all of the controls (including all text fields, check boxes, drop-down lists, and buttons) that people can use in order to complete and submit the forms?

- [x]  If your website has online forms, does the default setting in drop-down lists describe the information being requested instead of displaying a response option (e.g., “your age” instead of “18 - 21”)?

- [x] If a webpage has data charts or tables, is HTML used to associate all data cells with column and row identifiers?

- [x]   Do all video files on your website have audio descriptions of what is being displayed to provide access to visually conveyed information for people who are blind or have low vision?

- [x]  Do all video files on your website have written captions of spoken communication synchronized with the action to provide access to people who are deaf or hard of hearing?

- [x] Do all audio files on your website have written captions of spoken communication synchronized with the action to provide access to people who are deaf or hard of hearing?

- [x] Have all webpages been designed so they can be viewed using visitors’ web browser and operating system settings for color and font?

*Website Accessibility Policy and Procedures*

*This section will help you identify potential problems with the ongoing process of
ensuring website accessibility*

- [x]  Do you have a written policy on website accessibility?

- [x] Is the website accessibility policy posted on your website in a place where it can be easily located?

- [x] Have procedures been developed to ensure that content is not added to your website until it has been made accessible?

- [x]  Does the website manager check the HTML of all new webpages to confirm accessibility before the pages are posted?

- [x]  When documents are added to your website in PDF format, are text-based versions of the documents (e.g., HTML, RTF, or word processing format) added at the same time as the PDF versions?

- [x] Have in-house staff and contractors received information about the website accessibility policy and procedures to ensure website accessibility?


- [x] Have in-house and contractor staff received appropriate training on how to ensure the accessibility of your website?

- [x]  Have in-house and contractor staff who create web content or post it on your website received copies of the Department of Justice’s technical assistance document “Accessibility of State and Local Government Websites to People with Disabilities”?

- [x]  If your website contains inaccessible content, is a specific written plan including timeframes in place now to make all of your existing web content accessible?


- [x] Have you posted on your website a plan to improve website accessibility and invited suggestions for improvements?


- [x] Does your website home page include easily locatable information, including a telephone number and email address, for use in reporting website accessibility problems and requesting accessible services and information?


- [x] Do you have procedures in place to assure a quick response to website visitors with disabilities who are having difficulty accessing information or services available via the website?

- [x] Have you asked disability groups representing people with a wide variety of disabilities to provide feedback on the accessibility of your website? (Note: Feedback from people who use a variety of assistive technologies is helpful in ensuring website accessibility.)

- [x] Have you tested your website using one of the products available on the Internet to test website accessibility? (Note: Products available for testing website accessibility include no-cost and low-cost options. These products may not identify all accessibility issues and may flag issues that are not accessibility problems. However, they are, nonetheless, a helpful tool in improving website accessibility.)

- [x] Are alternative ways of accessing web-based information, programs, activities, and services available for people with disabilities who cannot use computers?

</details>









