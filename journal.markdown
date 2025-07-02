---
layout: page
title: Journal
---

# Feel free to use this as a space to journal

<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>Journal App</title>
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    <div class="journal-container">
      <form id="journal-form">
        <textarea
          id="journal-input"
          class="journal-entry"
          placeholder="I am grateful for..."
          required
        ></textarea>
        <textarea
          class="journal-entry"
          placeholder="What's on your mind?"
          required
        ></textarea>
        <textarea
          class="journal-entry"
          placeholder="I feel ... today"
          required
        ></textarea>
        <br>
        <button type="submit" class="journal-submit" style="padding: 12px 24px; background-color:rgb(116, 116, 116); color: white; border: none; border-radius: 6px; font-size: 16px; cursor: pointer; transition: background 0.2s;">Add Entry</button>
      </form>
      <div id="entries-list"></div>
    </div>
    <script>
      const form = document.getElementById("journal-form");
      const textareas = form.querySelectorAll(".journal-entry");
      const entriesList = document.getElementById("entries-list");

      function formatDate(date) {
        return date.toLocaleDateString(undefined, {
          year: "numeric",
          month: "long",
          day: "numeric",
        });
      }

      function getEntryText(texts, date) {
        return (
          `Date: ${formatDate(date)}\n` +
          `I am grateful for:\n${texts[0]}\n\n` +
          `What's on your mind?:\n${texts[1]}\n\n` +
          `I feel ... today:\n${texts[2]}`
        );
      }

      function addEntry(texts, date) {
        const entryDiv = document.createElement("div");
        entryDiv.className = "journal-entry-block";
        entryDiv.innerHTML = `
            <p class="journal-date">${formatDate(date)}</p>
            <div class="journal-entry">
              <p><strong>I am grateful for:</strong><br>${texts[0].replace(
                /\n/g,
                "<br>"
              )}</p>
              <p><strong>What's on your mind?:</strong><br>${texts[1].replace(
                /\n/g,
                "<br>"
              )}</p>
              <p><strong>I feel ... today:</strong><br>${texts[2].replace(
                /\n/g,
                "<br>"
              )}</p>
            </div>
            <button class="copy-entry-btn" type="button">Copy Entry</button>
          `;
        entriesList.prepend(entryDiv);

        // Add copy functionality
        const copyBtn = entryDiv.querySelector(".copy-entry-btn");
        copyBtn.addEventListener("click", function () {
          const entryText = getEntryText(texts, date);
          navigator.clipboard.writeText(entryText).then(() => {
            copyBtn.textContent = "Copied!";
            setTimeout(() => (copyBtn.textContent = "Copy Entry"), 1500);
          });
        });
      }

      form.addEventListener("submit", function (e) {
        e.preventDefault();
        const values = Array.from(textareas).map((t) => t.value.trim());
        if (values.every((v) => v)) {
          addEntry(values, new Date());
          textareas.forEach((t) => (t.value = ""));
        }
      });
    </script>

  </body>
</html>

<br>
Journaling daily is a powerful habit that can help you reflect on your thoughts, track your progress, and cultivate gratitude. By taking a few moments each day to write, you can gain clarity, reduce stress, and foster personal growth. Whether you're noting what you're grateful for or simply expressing how you feel, consistent journaling can make a meaningful difference in your well-being.
