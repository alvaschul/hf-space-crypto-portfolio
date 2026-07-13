---
title: Crypto Dashboard + Portfolio
emoji: 💰
colorFrom: purple
colorTo: gray
sdk: static
sdk_version: static
app_file: index.html
pinned: false
---

# Crypto Dashboard + Portfolio

A static Hugging Face Space that shows live crypto prices (via the public
[CoinGecko](https://www.coingecko.com/en/api) API) and lets you track a personal
portfolio. Holdings are saved locally in your browser via `localStorage`.

## Features

- Live market overview for the top coins (refreshes every 60s)
- Add / update / remove holdings
- Portfolio total value in USD
- No backend, no build step — pure static HTML/CSS/JS

## Deploy

This folder is a self-contained Space. To publish it:

1. Create a new Space at https://huggingface.co/new-space
2. Choose **Static** as the SDK
3. Push this folder's contents to the Space's git repo, or import this repo

The `sdk: static` metadata above is what tells HF to serve `index.html` directly.

## Notes

- CoinGecko's free tier is rate-limited. If prices fail to load, wait a moment and refresh.
- Portfolio data never leaves your browser.
