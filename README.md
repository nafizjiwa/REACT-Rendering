# React-Rendering

#### REACT is Front-end framework.
#### JSX is a syntax extension for JavaScript so HTML is treated as expressions
#### JSX gets translated into JavaScript
#### Expressions are stored in variables, objects, arrays.
#### JSX produces React “elements”. 
#### JSX produces React “elements”. 
<br>
<br>

|To render in React we must know|||
|:---:|:----|:----:|
|1.|What content to render| The `WHAT`|
|2.|Where to place the content| The 'WHERE`|

#### We can create a React root using createRoot() and it's render() method to render JSX at the specified DOM element.
#### A React root’s render() method only updates DOM elements that have changed using the virtual DOM.

    const container = document.getElementById('app');

#### Here use the document object (gets the web page) and the document method (.getElementById) to get the element with id 'app' and store it in the variable container.

    const root = createRoot(container);

#### Create a React root from container and store it in root so we can render the JSX expression.  ` The 'WHERE' part of React rendering. `

    root.render(<h1>Hello world</h1>);
    
#### Use the .render() method of root to render the content passed in as an argument. ` The 'WHAT' part of React rendering. `

||'WHAT TO RENDER'|'WHERE TO RENDER'|
|:---:|:----:|:----:|
|root.render(WHAT, WHERE);| ||
|`const hello = <h1>Hello world</h1>;`| WHAT ||
|document.getElementById('app')| |WHERE |
|root.render(hello, document.getElementById('app'));| before comma `WHAT` | after comma `WHERE`|


### Render('argument') can be a JSX expression or a variable but they must evaluate to a JSX expression.

            root.render('VARIABLE'); ------------------------->     root.render(<h1>Hello world</h1>);
            root.render('JSX Expression'); ----------------->        root.render(<h1>Hello world</h1>);

### SELF CLOSING TAGS in JSX
----
// Fine, without the slash: <br>
`<br>` <br>
// Also fine in HTML WITH a slash but REQUIRED in JSX: <br>
`<br />` <br>

### Javascript within JSX expressions
----
Code in between the tags of a JSX element/tags `<h2>code here</h1>` will be read as JSX, not as regular JavaScript! READ AS TEXT just like HTML. <br>

To treat code between JSX tags as JavaScript. WRAP THE CODE IN `{ }` BRACES<br>

        root.render(<h1>2 + 3</h1>)     ---------> PRINTS 2 + 3
        root.render(<h1>{2 + 3}</h1>)     ---------> PRINTS 5
        
##### The curly braces are markers that signal the beginning and end of a JAVASCRIPT INJECTION into JSX.

### Variables in JSX expessions
----
Use variables in JSX expressions with curly braces `{ }`, even if those variables were declared outside the expression.<br>

        const variableName = "Print me to the screen";
        root.render(<h1>{variableName}</h1>); --->  PRINTS 'Prints me to the screen";
    
##### It’s common to use variables to set attributes

      // Use a variable to set the `height` and `width` attributes:
    const sideLength = "200px";
    const panda = (
      <img 
        src="images/panda.jpg" 
        alt="panda" 
        height={sideLength} 
        width={sideLength} />
    );
### Event Listeners in JSX
----

To create an event listener ADD an attribute onClick, mouseOver... Here we add onClick:

|Event Listener: attribute={attributes Value}|Attribute’s value should be a FUNCTION|
|:--:|:----|
|`<img onClick={clickAlert} />`|function clickAlert() {|
|| alert('You clicked this image!');|
|| }|


   
## WRITE JSX CONDITIONALS
### if and else statements
----

|Don't inject if and else statements between JSX tags. JSX should be injected within the clauses|
|:--:|
|if (condition){ JSX XPRESSION if this condition |
| } else (condition){ |
| JSX XPRESSION if this condition |
| }|
<br>

|SEMICOLONS (;) ARE NOT REQUIRED AFTER THE JSX EXPRESSION AS IS THE CASE IN JAVASCRIPT IF ELSE STATMENTS|
|:--:|
| if {result = 'positive';   <----  }|

### The Ternary Operator
----
    const headline = (
      <h1>
        { age >= drinkingAge ? 'Buy Drink' : 'Do Teen Stuff' }
      </h1>
    );

##### If age >= drinkingAge is TRUTHY then headline = `<h1>'Buy Drink'</h1>` or if FALSY then headline = `<h1>'Do Teen Stuff'</h1>`

### &&
----
&& works best for conditionals If the left side of && evaluates to true then the right side will render.

      <ul>
        { !baby && <li>Pizza</li> }
        { age > 15 && <li>Brussels Sprouts</li> }
      </ul>

### .map() in JSX
----
|Using .map() in JSX expression to create a list in an Array|
|:---:|
|const strings = ['Home', 'Shop', 'About Me'];|
|const listItems = `strings.map(string => <li>{string}</li>);`|
|`<ul>{listItems}</ul>`|  
    

### KEYS in JSX
----
Keys helps create LISTS and track them with an index #.

    const peopleList = people.map((person, i) => (
      // expression:
      <li key={'person_'+ i}>{person}</li>
        ));

    // root.render:
    root.render(<ul>{peopleList}</ul>);

### A CALL TO `React.createElement()`
----
When a JSX element is compiled, the compiler transforms the JSX element into the method: React.createElement().

    const greatestDivEver = <div>i am div</div>;
    //SAME AS 
    const greatestDivEver = React.createElement(
      "div",
      null,
      "i am div"
    );



