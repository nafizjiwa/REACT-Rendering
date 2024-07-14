# React-Rendering

### REACT is Front-end framework.
### JSX is a syntax extension for JavaScript to treat HTML as expressions
### JSX gets translated into JavaScript
### Expressions are stored in variables, objects, arrays,
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

            render.root('VARIABLE'); ------------------------->     root.render(<h1>Hello world</h1>);
            render.root('JSX Expression'); ----------------->        root.render(<h1>Hello world</h1>);

### SELF CLOSING TAGS in JSX
----
// Fine, without the slash: <br>
`<br>` <br>
// Also fine in HTML WITH a slash but REQUIRED in JSX: <br>
`<br />` <br>
### Javascript within JSX expressions
----
Code in between the tags of a JSX element `<h2>code here</h1>` will be read as JSX, not as regular JavaScript! JSX doesn’t add numbers—it reads them as text, just like HTML. <br>

You need a way to write code that says, “Even though I am located in between JSX tags, treat me like ordinary JavaScript and not like JSX.” <br>

You can do this by wrapping your code in curly braces. <br>

        root.render(<h1>2 + 3</h1>)     ---------> PRINTS 2 + 3
        root.render(<h1>{2 + 3}</h1>)     ---------> PRINTS 5
##### The curly braces are not JSX or JavaScript. 
##### They are markers that signal the beginning and end of a JavaScript injection into JSX.

### Variables in JSX expessions
----
Variables can be accessed while inside of a JSX expression, even if those variables were declared outside the expression.<br>

        const variableName = "Print me to the screen";
        root.render(<h1>{variableName}</h1>); --->  PRINTS 'Prints me to the screen";

    // Use a variable to set the `height` and `width` attributes:

    const sideLength = "200px";
    
##### It’s common to use variables to set attributes

    const sideLength = "200px";
    const panda = (
      <img 
        src="images/panda.jpg" 
        alt="panda" 
        height={sideLength} 
        width={sideLength} />
    );
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
| else { result = 'NOT positive';   <---- }|

### The Ternary Operator
----
    const headline = (
      <h1>
        { age >= drinkingAge ? 'Buy Drink' : 'Do Teen Stuff' }
      </h1>
    );

##### If age >= drinkingAge is TRUTHY headline = `<h1>'Buy Drink'</h1>` or if FALSY truthy headline = `<h1>'Do Teen Stuff'</h1>`

### &&
----
&& works best for conditionals that sometimes do an action and other times do nothing.
If the left side of && evaluates to true then the right side will render.

    <li>Applesauce</li>
        { !baby && <li>Pizza</li> }
        { age > 15 && <li>Brussels Sprouts</li> }
        { age > 20 && <li>Oysters</li> }
        { age > 25 && <li>Grappa</li> }
      </ul>

### .map() in JSX
----

    const strings = ['Home', 'Shop', 'About Me'];
    const listItems = strings.map(string => <li>{string}</li>);
    <ul>{listItems}</ul>

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



