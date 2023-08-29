---
layout: default
title: Text-to-Speech Example
description: An example page that converts user input to audio using Web Speech API.
---

## Text-to-Speech Example

<label for="userInput">Type your text:</label>
<textarea id="userInput" rows="4" cols="50"></textarea>

<button id="convertButton">Convert to Audio</button>

<audio id="audioElement" controls></audio>

<script>
  document.addEventListener('DOMContentLoaded', () => {
    const convertButton = document.getElementById('convertButton');
    const userInput = document.getElementById('userInput');
    const audioElement = document.getElementById('audioElement');

    convertButton.addEventListener('click', () => {
      const inputText = userInput.value;
      convertToAudio(inputText);
    });

    function convertToAudio(text) {
      const synth = window.speechSynthesis;
      const utterance = new SpeechSynthesisUtterance(text);

      synth.speak(utterance);

      utterance.addEventListener('end', () => {
        console.log('Audio conversion completed.');
      });
    }
  });
</script>
