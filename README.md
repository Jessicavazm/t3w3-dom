# DOM - Document Object Model

- JS DOM
- Finding and reading elements
- Creating and Deleting
- Editing Elements

### Querying Methods

- querySelector finds the first node that matches our search criteria. We can match for element tags, classes and ids.
    - let firstParagraph = document.querySelector("p") (for tags you don't need to use anything)
    - for classes you need to use DOT: document.querySelector(".class_name")
    - for ID you need to use HASH: document.querySelector("#id_name")
- querySelectorAll selects all of the matches.
    - let listItems = document.querySelectorAll("li")
- Except for getElementById (which only returns a single node, because there is only a single node per id), the getElementsBy variations all return a collection of nodes that match the criteria.Essentially, the big difference between querySelectorAll and getElementsBy is that querySelectorAll will return a static list, any change to the DOM will not update dynamically. 
    - let form = document.getElementById("page-form")
    - let allParagraphs = document.getElementsByTagName("p")
    - let odds = document.getElementsByClassName("odd")


### JavaScript innerHTML, innerText, and textContent

Used to set or return an HTML element's content in the DOM.
- The innerHTML property sets and returns the content of an element with new HTML content. It is NOT recommended to use innerHTML when inserting plain text.
- The innerText property returns the content of all elements, except for script and style elements. The returned content is visible plain text without any formatting. 
- One drawback to using innerText is that its value triggers a reflow due to its awareness of CSS styling.
- The textContent property returns the raw content with styling inside of all elements, but excludes the HTML element tags.

#### Remove a node or node's child

We can access the children of a node by calling the children method on the parent node. It returns an array of all children. Alternatively, we could call querySelector (or any of the query methods) on the parent node to access the children. To remove the first li of the first ul, we could do the following for example:

    let ul = document.querySelector("ul")
    let li1 = ul.children[0]
    ul.removeChild(li1)
