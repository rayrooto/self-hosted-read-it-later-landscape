# Self-Hosted Read-It-Later Landscape


> **Decision:** Use this landscape to decide whether to preserve URL metadata, readable text, rendered snapshots, or multi-format evidence; skip it if a browser bookmark is already durable enough for the task.
>
> **For:** researchers and knowledge workers building a durable reading and capture workflow  ·  **Not for:** users seeking only feed polling or a zero-maintenance hosted queue

This is a non-commercial, source-traceable decision guide. It normalizes upstream declarations; it does not claim that repository reachability proves functionality, security, maintenance, or fitness.

**Start here:** [Download the capture catalogue](assets/capture-durability-map.csv) — twelve projects, located upstream evidence, and explicit unknowns.

## Choose by workload


- Reading queue with saved article text: compare wallabag and Readeck.
- Bookmark catalogue with minimal state: compare linkding, Buku, and Shaarli.
- Team collections plus preservation: compare Linkwarden and LinkAce.
- Research-grade multi-format capture: ArchiveBox has the broadest preservation role and the largest dependency surface.
- Single-user bookmark server with optional ArchiveBox handoff: Espial makes that boundary explicit.

## Decide what survives a missing URL

A bookmark is not an offline article. An external archive submission is not a private local copy.

## Durability ladder


- **Readable article copies** — wallabag and Readeck turn pages into reading artifacts; test extraction failures and export, not only the reader UI.
- **Bookmark catalogues** — linkding, Buku, Shaarli, Slash, and Shiori organize links; some optionally save content, but URL metadata remains a distinct durability level.
- **Collections with preservation** — Linkwarden, Karakeep, LinkAce, and Espial add saved content or archive integrations with different multi-user and privacy assumptions.
- **Web evidence archive** — ArchiveBox invokes several capture tools and stores multiple representations; its dependency and storage model should be treated as a preservation system.


## Capture catalogue

| Project | Role | Content kept locally | Annotations and organization | Export or external handoff |
|---|---|---|---|---|
| Linkwarden | team link archive | In addition to preservation, Linkwarden provides a user-friendly reading and annotation experience that blends the simplicity of a “read-it-later” tool with the… | In addition to preservation, Linkwarden provides a user-friendly reading and annotation experience that blends the simplicity of a “read-it-later” tool with the… | > [!IMPORTANT] > To use the app you’ll first need a Linkwarden account. |
| Karakeep | capture inbox | Karakeep (previously Hoarder) is a self-hostable bookmark-everything app with a touch of AI for the data hoarders out there. | - LLM-based automatic tagging and summarization. With supports for local models using ollama! | - Bookmark importers from Chrome, Pocket, Linkwarden, Omnivore, Tab Session Manager. |
| wallabag | read-it-later service | Click, save and read it when you want. It extracts content so that you won't be distracted by pop-ups and cie. | Unknown in the frozen upstream README | > [!IMPORTANT] > The name of this project is wallabag — all lowercase, always. Not "Wallabag", not "WallaBag", not any other variation. Just plain, humble, all-… |
| Readeck | read-it-later service | Move bookmarks to archives or favorites and add as many labels as you want. | Highlight and annotate the important content of your bookmarks to easily find it later. | What's better than reading your collected articles on your e-reader? You can export any article to an e-book file (EPUB). You can even export a collection to a … |
| linkding | bookmark manager | - Automatically archive websites, either as local HTML file or on Internet Archive | - Organize bookmarks with tags | - Automatically archive websites, either as local HTML file or on Internet Archive - Import and export bookmarks in Netscape HTML format |
| Shiori | bookmark and readable-content manager | - Where possible, by default shiori will parse the readable content and create an offline archive of the webpage. | Shiori is a simple bookmarks manager written in the Go language. Intended as a simple clone of [Pocket][pocket]. You can use it as a command line application or… | - Import and export bookmarks from and to Netscape Bookmark file. - Import bookmarks from Pocket. |
| Shaarli | link log and sharing service | Unknown in the frozen upstream README | The personal, minimalist, super fast, database-free, bookmarking service. | Unknown in the frozen upstream README |
| ArchiveBox | web preservation system | ArchiveBox is a self-hosted app that lets you preserve content from websites in a variety of formats. | You can run ArchiveBox as a Docker web app to manage these snapshots, or continue accessing the same collection using the uv-installed CLI, Python API, and SQLi… | Once installed, you can interact with it through the: Browser Extension, CLI, self-hosted web interface, Python API, or filesystem. |
| LinkAce | bookmark archive | LinkAce ia a powerful, self-hosted solution for managing your personal link archive. Save articles for later reading, bookmark useful tools, and preserve import… | Organize bookmarks with the help of lists and tags. Multi-user support with internal sharing of links, lists or tags. | Import and export of bookmarks from and to HTML. |
| Buku | CLI bookmark manager | 39. Add a bookmark after following all permanent redirects, but only if the server doesn't respond with an error (and there's no network failure) | Unknown in the frozen upstream README | - Import/export bookmarks from/to HTML, XBEL, Markdown, RSS/Atom or Orgfile |
| Espial | multi-user bookmark server | Espial supports configurable archive backends for saving bookmark snapshots. | Espial is an open-source, web-based bookmarking server. | Espial also supports file import options (see CLI, or the settings -> Import / Export page in the web UI). |
| Slash | team link shortcut service | Unknown in the frozen upstream README | Slash is an open source, self-hosted platform designed to help you organize, manage, and share your most important links. Easily create customizable, human-read… | Slash is an open source, self-hosted platform designed to help you organize, manage, and share your most important links. Easily create customizable, human-read… |

Values are short excerpts from the frozen upstream README, not feature-test scores. The CSV retains the located evidence for each cell. “Unknown” means the retrieved document did not establish that axis; it is not a claim that the feature is absent.

## Assemble the minimal stack


A low-friction pattern is a browser/mobile capture client feeding a bookmark or reading service, with selected high-value URLs exported to ArchiveBox. Avoid archiving every private page into a globally shared index. Before migration, export URLs and tags, then separately confirm whether saved article bodies, screenshots, and annotations leave the old system.


## Adoption notes by project

### Linkwarden

- **Choose it for:** Teams wanting collaboration and page preservation.
- **License at the frozen source:** [AGPL-3.0](https://raw.githubusercontent.com/linkwarden/linkwarden/24adcc146ba356632859a1e8adb4bffae2874d11/LICENSE.md).
- **Adoption test:** Test export of links, tags, annotations, and preserved assets separately; define storage growth and backup.
- **Source:** [linkwarden/linkwarden](https://github.com/linkwarden/linkwarden).

### Karakeep

- **Choose it for:** Fast personal capture across mixed media.
- **License at the frozen source:** [AGPL-3.0](https://raw.githubusercontent.com/karakeep-app/karakeep/337161a5f9ef9a3d40d6229aba353d625897bb6d/LICENSE).
- **Adoption test:** Optional AI and video capture add dependencies; verify export fidelity without those services.
- **Source:** [karakeep-app/karakeep](https://github.com/karakeep-app/karakeep).

### wallabag

- **Choose it for:** Mature article-reading workflows.
- **License at the frozen source:** [MIT](https://raw.githubusercontent.com/wallabag/wallabag/995ca0078f0dd0ad25af60c4ab39b40195e15f49/COPYING.md).
- **Adoption test:** Extraction quality varies by site; test client API, annotations, and full export using difficult pages.
- **Source:** [wallabag/wallabag](https://github.com/wallabag/wallabag).

### Readeck

- **Choose it for:** Focused reading queue with an official non-GitHub upstream.
- **License at the frozen source:** [AGPL-3.0](https://codeberg.org/readeck/readeck/raw/commit/dd31edd071dcf5ca074dc197f3b0161cd262b890/LICENSE).
- **Adoption test:** The GitHub repository is only a pointer; use Codeberg as canonical and test browser capture and export.
- **Source:** [readeck/readeck](https://codeberg.org/readeck/readeck).

### linkding

- **Choose it for:** Minimal durable bookmark catalogue.
- **License at the frozen source:** [MIT](https://raw.githubusercontent.com/sissbruecker/linkding/27b7303baf41bb28babc610ac8eaa486e1ddfab5/LICENSE.txt).
- **Adoption test:** Optional archive behavior is not equivalent to a complete evidence snapshot; test backups and imports.
- **Source:** [sissbruecker/linkding](https://github.com/sissbruecker/linkding).

### Shiori

- **Choose it for:** Single-user capture that can save a readable copy.
- **License at the frozen source:** [MIT](https://raw.githubusercontent.com/go-shiori/shiori/aebb4021a56048eed4c8feb325399be5f46e5470/LICENSE).
- **Adoption test:** The web extension is marked beta; confirm content/image preservation and export before relying on offline copies.
- **Source:** [go-shiori/shiori](https://github.com/go-shiori/shiori).

### Shaarli

- **Choose it for:** A compact personal link journal.
- **License at the frozen source:** [zlib](https://raw.githubusercontent.com/shaarli/Shaarli/6ecde7a382de51f5f14bb3978c5405a5665fe860/COPYING).
- **Adoption test:** It is not a full-page preservation system; test authentication, plugins, and data export for your deployment.
- **Source:** [shaarli/Shaarli](https://github.com/shaarli/Shaarli).

### ArchiveBox

- **Choose it for:** Research or evidence capture where multiple representations matter.
- **License at the frozen source:** [MIT](https://raw.githubusercontent.com/ArchiveBox/ArchiveBox/c76067d210a619dd1baa9a3f3c6f06f2a64d5a48/LICENSE).
- **Adoption test:** Dependencies, browser versions, private-page permissions, storage growth, and restoration all need a real capture set.
- **Source:** [ArchiveBox/ArchiveBox](https://github.com/ArchiveBox/ArchiveBox).

### LinkAce

- **Choose it for:** Organized personal or team link collections.
- **License at the frozen source:** [GPL-3.0](https://raw.githubusercontent.com/Kovah/LinkAce/ebdcb38ea40b578c3678603bb2eb1096d77cb534/LICENSE.md).
- **Adoption test:** Kubernetes setup and managed hosting are marked beta; Internet Archive submission is not a private local copy.
- **Source:** [Kovah/LinkAce](https://github.com/Kovah/LinkAce).

### Buku

- **Choose it for:** Keyboard-oriented users wanting portable local metadata.
- **License at the frozen source:** [GPL-3.0](https://raw.githubusercontent.com/jarun/buku/7881fae49651555478b83d254de4609c1810daf2/LICENSE).
- **Adoption test:** It does not preserve complete pages by default; test import/export and browser integration separately.
- **Source:** [jarun/buku](https://github.com/jarun/buku).

### Espial

- **Choose it for:** A small multi-user bookmark service with explicit archive adapters.
- **License at the frozen source:** [AGPL-3.0](https://raw.githubusercontent.com/jonschoning/espial/27f1d4bcdc537c0182886f7fc22c1fcf0befa6e6/LICENSE).
- **Adoption test:** Its ArchiveBox adapter uses a global index and is best suited to single-user instances; change example credentials and back up SQLite.
- **Source:** [jonschoning/espial](https://github.com/jonschoning/espial).

### Slash

- **Choose it for:** Teams organizing frequently shared destinations.
- **License at the frozen source:** [AGPL-3.0](https://raw.githubusercontent.com/yourselfhosted/slash/e5a4508b797a5fbdd7c633146152b14a5aba9061/LICENSE).
- **Adoption test:** It optimizes link naming and sharing, not article extraction or durable page preservation.
- **Source:** [yourselfhosted/slash](https://github.com/yourselfhosted/slash).

## Export the reading state

1. Capture a plain article, an image-heavy page and a permitted authenticated page.
2. Disconnect the origin and check which content remains local.
3. Export URLs/tags separately from saved bodies, annotations and attachments.
4. Restore an isolated index and confirm that private captures remain private.

## What this guide covers

Human reading copies, bookmarks and preserved pages, not generic note-taking or agent memory.

## Adjacent guides

- [self-hosted-rss-reader-comparison](https://github.com/MargaritaOfficial/self-hosted-rss-reader-comparison) — Use it when the upstream problem is feed polling, filtering, user separation, and client access.
- [open-source-document-workflow-index](https://github.com/mckee19/open-source-document-workflow-index) — Use it when captured pages become governed records that need OCR, retrieval, retention, or preservation.
- [encrypted-backup-tool-selector](https://github.com/Anguianodd/encrypted-backup-tool-selector) — Use it when captures, databases, and reading state need a verified recovery path.

## Located sources and update policy

[`sources.json`](sources.json) binds each cited declaration to a commit, document, exact line range and local snapshot hash. [`assets/projects.json`](assets/projects.json) holds the normalized roles and decision axes. Current HEAD reachability is recorded separately; it is not a maintenance or security assessment. Licensing is version- and directory-specific. Re-read the selected release before adoption.

Run the local evidence and package checks, then opt into public-source reachability:

```bash
python3 scripts/verify_sources.py
python3 scripts/verify_sources.py --online
```

These checks validate source binding, excerpts, hashes, language, the decision asset and nonempty public content. They do not certify feature behavior, migration success or restore success. No popularity score, paid placement or affiliate ranking is used. Restricted-license and historical examples are explicit contrasts, not silently recommended open-source defaults.

If this saved you a decision, star the repo — it is how the next reader finds it.
