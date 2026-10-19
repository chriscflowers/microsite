# Aviator demos & research (GitHub Pages)

No build step and no scripts: only HTML, Markdown, and one small config file.
GitHub Pages converts the Markdown notes to web pages automatically.

## Publish a note from Obsidian
1. In Obsidian, turn off Settings → Files and links → "Use [[Wikilinks]]" so links between notes
   are written as standard Markdown links. Name published files in lowercase-with-dashes.
2. Make sure the note starts with properties (frontmatter), e.g. `title`, `topic`, `date`, `status`.
3. Copy the .md file into `notes/`. It appears at `notes/<filename>.html`.
4. Add a card for it in `research.html` (and optionally `index.html`): copy an existing
   `<a class="card" ...>` block and edit the topic, date, title, summary, and link.
   Keep `data-topic` equal to the lowercase topic name.
5. Commit and push. In the repo: Settings → Pages → deploy from branch, `/ (root)`.

## Add a topic filter
In `research.html`, copy one radio + label pair, change `f-overview` / `Overview` to your topic,
then add a line to the CSS: `#f-yourtopic:checked~.grid .card:not([data-topic=yourtopic]){display:none}`.

Not supported: Obsidian callouts, Dataview, embedded notes. Images go in `notes/attachments/`.
Note pages render only on GitHub Pages (or with Jekyll); research.html and index.html also work if opened directly.
