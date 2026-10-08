# UTV Hott News bilingual Canva carousel skill

![UTV Hott News Canva carousel engine workflow](assets/workflow.png)

Give an agent with this skill a UTV Hott News article link **or a news screenshot**. It reads the article or visible screenshot information, drafts Telugu and English copy, builds matching four-page Canva imports, checks the requested language designs, and returns Canva edit links. When a screenshot has no usable story photo, it makes a text-led cover. Page four invites readers to download UTV Hott News App for more news on the story's topic.

Each page uses the small UTV Hott News logo at top left and a white Instagram icon with `@utvhottnewsapp` at bottom right. The original yellow, black, red, and white palette and fonts are preserved.

Shapes and their labels are separate editable layers. Text is centered above each shape, including fact cards, number circles, badges, the app download panel, and the footer.

The last slide includes the supplied App Store and Google Play badges below the app download panel.

See [SKILL.md](SKILL.md) for the workflow and [platform instructions](references/platforms.md) for ChatGPT, Claude, Codex, Google Antigravity, Windows, and Mac.

The local generator needs Python 3.11+. The agent prepares the bilingual story JSON from the source; the generator packages the designs and does not perform OCR. For an article with a photo:

```sh
python3 scripts/build_carousel.py --story examples/story.example.json --image article.jpeg --output out-first-story
```

For a screenshot without a usable photo, omit `source_url` from the story JSON and run:

```sh
python3 scripts/build_carousel.py --story screenshot-story.json --screenshot screenshot.png --output out-screenshot-story
```

You can also pass `--image` with a screenshot story when a suitable source photo is available.

On Windows, replace `python3` with `py -3`. The ZIP outputs are imported into Canva as separate four-page designs. A Canva connection is required to return edit links automatically.
