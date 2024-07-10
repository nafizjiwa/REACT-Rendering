# React-Rendering

|To render in React we must know|||
|:---:|:----|:----:|
|1.|What content to render| The `WHAT`|
|2.|Where to place the content| The 'WHERE`|

Wwe saw how we can create a React root using createRoot() and use its render() method to render JSX.

    const container = document.getElementById('app');

#### Here use the document object (gets the web page) and the document method (.getElementById) to get the element with id 'app' and store it in the variable container.

    const root = createRoot(container);

#### Create a React root from container and store it in root so we can render the JSX expression.  ` The 'WHERE' part of React rendering. `

    root.render(<h1>Hello world</h1>);
    
#### Use the .render() method of root to render the content passed in as an argument. ` The 'WHAT' part of React rendering. `
