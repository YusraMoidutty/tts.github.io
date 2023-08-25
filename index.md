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
  <textarea id="text-input" name="user-text" rows="7" cols="90"></textarea>
  <br><br><br>
  <button type="button" id="convertButton" class="btn btn-custom">Convert To Audio</button>
</form>

<hr class="centered-line">

<p class="centered-text">You can add either Text / PDF</p>

<!-- Include your JavaScript code here -->
<script>
  document.addEventListener('DOMContentLoaded', () => {
    const convertButton = document.querySelector('.btn-custom');
    const userInput = document.getElementById('text-input');
    const audioElement = document.getElementById('audioElement');

    convertButton.addEventListener('click', async () => {
      try {
        const text = userInput.value;
        
        // Load the model (replace the URL with the actual model URL)
        const model = await tf.loadLayersModel("https://github.com/YusraMoidutty/tts.github.io/releases/download/v1.0/model_weights.hdf5");

        // Process the text and generate audio (replace with your actual code)
        const audioData = await generateAudioFromText(model, text);

        // Set audio data as a playable source
        const audioUrl = URL.createObjectURL(new Blob([audioData], { type: 'audio/wav' }));
        audioElement.src = audioUrl;
        audioElement.play();
      } catch (error) {
        console.error('Error:', error);
      }
    });
  });
</script>

