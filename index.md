---
layout: default
title: Malayalam TTS
description: Convert Your Text To Speech.
---

<link rel="stylesheet" href="styles.css">

<h2 class="centered-text" style="font-weight: bold;">Malayalam TTS</h2>

<h3>Text to Speech Conversion TTS</h3>

<form action="process-text" method="post">
  <label for="text-input">Type your text:</label>
  <textarea id="text-input" name="user-text" rows="4" cols="50"></textarea>
  <br><br><br>
  <button type="button" id="convertButton" class="btn btn-custom">Convert To Audio</button>
</form>

<hr class="centered-line">

<p class="centered-text">You can add either Text / PDF</p>

<!-- Include your JavaScript code here -->
<script>
  document.getElementById('convertButton').addEventListener('click', async () => {
    try {
      const userInput = document.getElementById('text-input').value;
      const model = await tf.loadLayersModel("https://github.com/YusraMoidutty/tts.github.io/releases/download/v1.0/model_weights.hdf5");
      // Rest of your code for generating audio
    } catch (error) {
      console.error('Error:', error);
    }
  });
</script>
