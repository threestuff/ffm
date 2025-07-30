---
layout: page
title: Routine
permalink: /routine/
---

<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <meta name="viewport" content="width=device-width, initial-scale=1.0" />
        <title>One Video Generator</title>
    </head>
    <body>
        <h3>Yoga, Qigong, Activation, Breathing Exercise, Meditation</h3>
        <h4>"Use these short routines to encourage yourself" - Jeffery Chang</h4>
        <div align="left" style="margin: 24px 0;">
                <button id="generateBtn" style="padding: 12px 24px; background-color:rgb(116, 116, 116); color: white; border: none; border-radius: 6px; font-size: 16px; cursor: pointer; transition: background 0.2s;">
                        Click to Generate Video
                </button>
        </div>
        <div id="videos" align="center"></div>
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

        <h2>Videos</h2>

<ul>
    <li>
        <a href="https://www.youtube.com/watch?v=8sJ5N9nsEmM" target="_blank">13 Minutes of Body Activation / Loosening Exercises for the Morning with Shi Heng Yi
        </a>
    </li>
    <li>
        <a href="https://www.youtube.com/watch?v=3GtFp6sz5zM" target="_blank">
Qigong to Purge and Tonify
        </a>
    </li>
    <li>
        <a href="https://www.youtube.com/watch?v=Y88zYo0YlOo" target="_blank">Daily Qigong Routine - Easy and Effective!
        </a>
    </li>
    <li>
        <a href="https://www.youtube.com/watch?v=VJ7QlwZPCQ8" target="_blank">DAILY ENERGY RECHARGE
        </a>
    </li>
    <li>
        <a href="https://www.youtube.com/watch?v=9WJfaL1NiJA" target="_blank">Qigong for Healthy Boundaries with Jeff Chand
        </a>
    </li>
    <li>
        <a href="https://www.youtube.com/watch?v=o_73FeXw3ZI" target="_blank">Start your day with this!
        </a>
    </li>
    <li>
        <a href="https://www.youtube.com/watch?v=ZhQ_2JU4Nv8" target="_blank">10 Minute Yoga Flow Practice for Strength, Stability and Focus
        </a>
    </li>
    <li>
        <a href="https://www.youtube.com/watch?v=PzSVekqNiuA" target="_blank">The Best Thing To Do In The Mornings
        </a>
    </li>
    <li>
        <a href="https://www.youtube.com/watch?v=q_x_4UsytgY" target="_blank">
Energization Exercises of Paramhansa Yogananda
        </a>
    </li>
    <li>
        <a href="https://www.youtube.com/watch?v=lwlEJ2O-6HM" target="_blank">Breathing Techniques to Release DMT! (MUST TRY)
        </a>
    </li>
    <li>
        <a href="https://www.youtube.com/watch?v=gCyoa2XPV5o" target="_blank">20 Minute Meditation Session
        </a>
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

            let lastIndex = -1;

            document
                .getElementById("generateBtn")
                .addEventListener("click", function () {
                    let randomIndex;
                    do {
                        randomIndex = Math.floor(Math.random() * youtubeVideos.length);
                    } while (youtubeVideos.length > 1 && randomIndex === lastIndex);

                    lastIndex = randomIndex;
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
