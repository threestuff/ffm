---
layout: page
title: Simple Exercise Generator
---

<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>One Video Generator</title>
  </head>
  <body>
    <h3>Yoga, Qigong, Activation, Breathing Exercise, Meditation</h3>
    <h4>"Use these short routines to encourage yourself"</h4>
    <div align="left" style="margin: 24px 0;">
        <button id="generateBtn" style="padding: 12px 24px; background-color:rgb(116, 116, 116); color: white; border: none; border-radius: 6px; font-size: 16px; cursor: pointer; transition: background 0.2s;">
            Click to Generate Video
        </button>
    </div>
    <div id="videos"></div>
    <h2>Creators</h2>
    <ul>
      <li>
        <a href="https://www.youtube.com/@BreatheAndFlow" target="_blank"
          >@BreatheAndFlow</a
        >
      </li>
      <li>
        <a href="https://www.youtube.com/@shaolin.online" target="_blank"
          >@Shaolin.Online</a
        >
      </li>
      <li>
        <a href="https://www.youtube.com/@ThinkVitalityQiGong" target="_blank"
          >@ThinkVitalityQiGong</a
        >
      </li>
      <li>
        <a href="https://www.youtube.com/@yoqi" target="_blank">@yoqi</a>
      </li>
      <li>
        <a href="https://www.youtube.com/@expandinglightretreat" target="_blank"
          >@ExpandingLightRetreat</a
        >
      </li>
      <li>
        <a href="https://www.youtube.com/@clarkkegley" target="_blank"
          >@clarkkegley</a
        >
      </li>
      <li>
        <a href="https://www.youtube.com/@KriyaYogaOnline">@KriyaYogaOnline</a>
      </li>
    </ul>

    <script>
      const youtubeVideos = [
        "8sJ5N9nsEmM",
        "3GtFp6sz5zM",
        "Y88zYo0YlOo",
        "VJ7QlwZPCQ8",
        "9WJfaL1NiJA",
        "o_73FeXw3ZI",
        "ZhQ_2JU4Nv8",
        "PzSVekqNiuA",
        "q_x_4UsytgY",
        "lwlEJ2O-6HM",
        "gCyoa2XPV5o",
      ];

      document
        .getElementById("generateBtn")
        .addEventListener("click", function () {
          const randomIndex = Math.floor(Math.random() * youtubeVideos.length);
          const videoId = youtubeVideos[randomIndex];

          const iframe = document.createElement("iframe");
          iframe.src = `https://www.youtube.com/embed/${videoId}`;
          iframe.width = "560";
          iframe.height = "315";
          iframe.allow =
            "accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture";
          iframe.allowFullscreen = true;

          const container = document.getElementById("videos");
          container.innerHTML = ""; // Clear previous
          container.appendChild(iframe);
        });
    </script>

  </body>
</html>
