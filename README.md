# React-Rendering

|To render in React we must know||
|:---:|:----|
|1.|What content to render|
|2.|Where to place the content|


    const container = document.getElementById('app');
This line:

Uses the document object which represents our web page.
Uses the getElementById() method of document to get the Element object representing the HTML element with the passed in id (app).
Stores the element in container.

    const root = createRoot(container);
we use createRoot() from the react-dom/client library, which creates a React root from container and stores it in root. root can be used to render a JSX expression. This is the “where to place the content” part of React rendering.

    root.render(<h1>Hello world</h1>);
    
uses the render() method of root to render the content passed in as an argument. Here we pass an <h1> element, which displays Hello world. This is the “what content to render” part of React rendering.
