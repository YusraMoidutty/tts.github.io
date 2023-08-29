---
layout: default
title: Process Text
description: Processing User-Input Text
---

<link rel="stylesheet" href="styles.css">

# Processed Text

{% if page.user-text %}
<p>You typed:</p>
<p>{{ page.user-text }}</p>
{% else %}
<p>No text submitted.</p>
{% endif %}

<a href="/">Go back</a>

<script src="script.js"></script> <!-- Include the JavaScript file -->
