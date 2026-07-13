# HF Spaces Template Repo

A collection of ready-to-deploy [Hugging Face Spaces](https://huggingface.co/spaces),
organized as self-contained folders. Each folder under `spaces/` is a complete,
independently deployable Space.

## Layout

```
.
├── README.md                     # this file
└── spaces/
    └── crypto-portfolio/         # one folder per Space
        ├── README.md             # HF Space metadata (sdk: static, etc.)
        └── index.html            # the Space's app file
```

## How to add a new Space

1. Create a folder: `spaces/<your-space-name>/`
2. Add a `README.md` with the HF frontmatter:

   ```yaml
   ---
   title: My Space
   emoji: 🚀
   colorFrom: blue
   colorTo: red
   sdk: static          # or gradio / streamlit / docker
   sdk_version: static
   app_file: index.html # entrypoint
   pinned: false
   ---
   ```

3. Add your app file(s) (`index.html`, `app.py`, `streamlit_app.py`, …).
4. Push the folder to a new HF Space repo, or import this repo.

## Static vs framework Spaces

- **static** (`sdk: static`): plain HTML/CSS/JS, no build. Great for dashboards
  and demos. See `spaces/crypto-portfolio`.
- **gradio / streamlit / docker**: for Python apps. Swap the frontmatter
  `sdk`/`app_file` accordingly and add a `requirements.txt` when needed.

## Deploying

For each Space, create a Space on HF and push that folder's contents:

```bash
cd spaces/crypto-portfolio
git init
git add .
git commit -m "init space"
git remote add space https://huggingface.co/spaces/<user>/<space-name>
git push -u space main
```
