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
  <title>JavaScript DOM Manipulation Example</title>
  <link rel="stylesheet" href="styles.css" />
</head>
<body>
  <header>
    <h1 id="main-title">Welcome to My Page</h1>
  </header>

  <nav>
    <button id="toggle-btn">Add Paragraph</button>
  </nav>

  <main>
    <section>
      <p id="dynamic-text">This text will change dynamically.</p>
    </section>

    <article id="extra-content">
      <!-- Extra paragraph will be added/removed here -->
    </article>
  </main>

  <footer>
    <small>© 2025 Your Name</small>
  </footer>

  <script src="script.js"></script>
</body>
</html>


// Change text content dynamically after 2 seconds
setTimeout(() => {
  const dynamicText = document.getElementById('dynamic-text');
  dynamicText.textContent = 'The text has been changed by JavaScript!';
}, 2000);

// Modify CSS style dynamically
const mainTitle = document.getElementById('main-title');
mainTitle.style.color = 'darkblue';
mainTitle.style.fontFamily = 'Arial, sans-serif';

// Add or remove a paragraph when button clicked
const button = document.getElementById('toggle-btn');
const extraContent = document.getElementById('extra-content');

button.addEventListener('click', () => {
  if (!document.getElementById('added-paragraph')) {
    const newParagraph = document.createElement('p');
    newParagraph.id = 'added-paragraph';
    newParagraph.textContent = 'This paragraph was added dynamically!';
    newParagraph.style.color = 'green';
    extraContent.appendChild(newParagraph);
    button.textContent = 'Remove Paragraph';
  } else {
    const para = document.getElementById('added-paragraph');
    extraContent.removeChild(para);
    button.textContent = 'Add Paragraph';
  }
});
