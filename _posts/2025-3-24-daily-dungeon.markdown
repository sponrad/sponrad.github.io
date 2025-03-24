---
layout: post
title:  "Dungeon Daily"
date:   2025-03-24
categories: ai
comments: true
---
Daily dungeon game kinda like Wordl.

<style>
.game-container {
    position: relative;
    width: 100%;
    max-width: 600px;
    padding-bottom: 180%; /* aspect ratio (height/width) */
    margin: 0 auto;
}

.game-container iframe {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    max-height: 800px;
    min-height: 650px;
    border: none;
}
</style>

<button onclick="document.getElementById('game-frame').requestFullscreen()">Fullscreen</button>
<div class="game-container">
    <iframe src="https://raw.githack.com/sponrad/dungeondaily/refs/heads/main/index.html"
            title="Game"
            allowfullscreen="true"
            id="game-frame"></iframe>
</div>

[https://github.com/sponrad/dungeondaily](https://github.com/sponrad/dungeondaily)
