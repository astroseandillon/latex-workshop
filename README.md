# latex-workshop

## :rocket: Start [here](guide/introduction.md) for the step-by-step guide.

[How to Contribute](guide/contributing.md)

[Roadmap](roadmap.md)

## Overview

- What is LaTeX and why do we want to use it?
- Citation management
- Collaboration with GitHub

## LaTeX

LaTeX is a typesetting system that produces really beautiful PDF documents.
It has a lot of benefits over other word processing software:
- Cross-platform, free, and open source.
- Use any text editor you like.
- Easy and fast reference management.
- Focus on writing content, not formatting.
- Easy handling of mathematical notation and equations.
- Re-submitting an article to a different journal? No problem, just download that journal's LaTeX style, change one line in your document, and re-compile.

### Editors

[Overleaf](https://www.overleaf.com/)
- Easy to get started.
- Requires a free account.
- Limited to one collaborator with free accounts.
- Not very customizable.

[TeXstudio](https://www.texstudio.org/)
- Includes some nice features like code completion.

[Visual Studio Code (VSCode)](https://code.visualstudio.com/)
- Very customizable and extensible.
- Requires a couple of plugins and a little bit of setup.
- Work on LaTeX and other code (like Python) in different tabs of the same editor, with a consistent user interface and keyboard shortcuts.

[WebLaTeX](https://github.com/sanjib-sen/WebLaTex)
- A web-based VSCode editor that runs in a GitHub codespace.
- Supports live collaboration and GitHub integration.
- A nice free alternative to Overleaf.
- Codespaces are limited to 60 hours per month for the free plan.

[Neovim](https://neovim.io/)
- The hardest to get started with.
- After a learning curve, it can be the fastest editor.
- Very lightweight and has a wide variety of plugins.

## Citation Management

LaTeX comes with BibTeX, which stores references as easy to read entries in a plain text file.
BibTeX files can be exported from libraries and journal websites.
Full featured citation managers such as [Zotero](https://www.zotero.org/) can be set up to export in BibTex format, and help you keep an organized collection of PDFs.

## Collaboration with GitHub

GitHub is a repository host and frontend for the version control software Git. Used to manage multiple collaborators on large software projects, it's more than adequate to handle LaTeX documents.

Handling your documents through a GitHub repository gives you an off-site backup, easy tracking of changes and revisions, simple handling of merge conflicts, and access to prior versions of your document.

## Helpful Links

The following are resources I learned from and used to prepare this workshop.

[Overleaf documentation](https://www.overleaf.com/learn)

[A git quickstart guide for LaTeX users](https://www.math.cmu.edu/~gautam/sj/blog/20130929-git-quickstart.html)
