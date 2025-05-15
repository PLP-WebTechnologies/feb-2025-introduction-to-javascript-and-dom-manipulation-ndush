# Introduction to JavaScript and DOM Manipulation

## Objectives

Write basic JavaScript functions.
Manipulate the DOM dynamically.
Respond to user interactions.

## Instructions

- Create a script.js file and link it to a HTML.
- Structure the document using DOCTYPE, html, head, and body.

>[!NOTE]
>  - Write JavaScript that:
>  - Changes text content dynamically.
>  - Modifies CSS styles via JavaScript.
>  - Adds or removes an element when a button is clicked.


# Tasks
- Create a well-structured HTML5 document.
- Use at least 5 different HTML elements.
- Ensure semantic correctness.




<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Dynamic Content Example</title>
  <link rel="stylesheet" href="styles.css" />
  <script src="script.js" defer></script>
</head>
<body>
  <header>
    <h1 id="main-title">Welcome to My Page</h1>
  </header>

  <nav>
    <ul>
      <li><a href="#section1">Intro</a></li>
      <li><a href="#section2">Features</a></li>
    </ul>
  </nav>

  <main>
    <section id="section1">
      <h2>Introduction</h2>
      <p id="intro-text">This paragraph will update dynamically.</p>
    </section>

    <section id="section2">
      <h2>Interactive Section</h2>
      <button id="toggle-btn">Add Element</button>
      <div id="dynamic-container"></div>
    </section>
  </main>

  <footer>
    <small>&copy; 2025 My Website</small>
  </footer>
</body>
</html>



document.addEventListener('DOMContentLoaded', () => {
  const introText = document.getElementById('intro-text');
  const mainTitle = document.getElementById('main-title');
  const toggleBtn = document.getElementById('toggle-btn');
  const container = document.getElementById('dynamic-container');

  // Change text content dynamically
  introText.textContent = 'Here is some updated text content added via JavaScript.';

  // Modify CSS styles dynamically
  mainTitle.style.color = 'darkblue';
  mainTitle.style.fontFamily = 'Arial, sans-serif';

  // Toggle adding/removing an element on button click
  toggleBtn.addEventListener('click', () => {
    if (container.childElementCount === 0) {
      const newElement = document.createElement('p');
      newElement.textContent = 'This element was added dynamically!';
      newElement.style.backgroundColor = '#eef';
      newElement.style.padding = '10px';
      newElement.style.borderRadius = '5px';
      container.appendChild(newElement);
      toggleBtn.textContent = 'Remove Element';
    } else {
      container.innerHTML = '';
      toggleBtn.textContent = 'Add Element';
    }
  });
});

Happy Coding! 💻✨
