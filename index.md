---
layout: default
title: Text Input Example
description: An example page with a text area for user input.
---

## Text Input Example

<label for="userInput">Type your text:</label>
<textarea id="userInput" rows="4" cols="50"></textarea>

<button id="helloButton">Click Me</button>

<script>
  document.addEventListener('DOMContentLoaded', () => {
    const helloButton = document.getElementById('helloButton');
    const userInput = document.getElementById('userInput');

    helloButton.addEventListener('click', () => {
      const inputText = userInput.value;
      console.log('User input:', inputText);
    });
  });
</script>
