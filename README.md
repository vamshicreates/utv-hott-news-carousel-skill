# UTV Hott News bilingual Canva carousel skill

Give a UTV Hott News article link to an agent with this skill installed. It reads the article, drafts Telugu and English copy, uses the article's lead image, builds matching three-page Canva imports, checks both designs, and returns two Canva edit links.

See [SKILL.md](SKILL.md) for the workflow and [platform instructions](references/platforms.md) for ChatGPT, Claude, Codex, Google Antigravity, Windows, and Mac.

The local generator needs Python 3.11+ and the article's downloaded lead photo. Example:

```sh
python3 scripts/build_carousel.py --story examples/story.example.json --image article.jpeg --output out-first-story
```

On Windows, replace `python3` with `py -3`. The two ZIP outputs are imported into Canva as separate three-page designs. A Canva connection is required to return edit links automatically.
