# TeamTex (TMT)

[![Version](https://img.shields.io/badge/version-v1.0.0-blue.svg)](https://github.com/yursds/teamtex/releases)
[![Docker Build](https://github.com/yursds/teamtex/actions/workflows/docker-publish.yml/badge.svg)](https://github.com/yursds/teamtex/actions/workflows/docker-publish.yml)
[![LaTeX Build](https://github.com/yursds/teamtex/actions/workflows/latex-check.yml/badge.svg)](https://github.com/yursds/teamtex/actions/workflows/latex-check.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Repo Size](https://img.shields.io/github/repo-size/yursds/teamtex)](https://github.com/yursds/teamtex)
[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/yursds/teamtex)

TeamTex is a lightweight and customizable LaTeX environment built for Dev Containers, GitHub Codespaces, and robust local usage.

---

<p align="center">
  <img src="docs/img/meme.jpg" alt="TeamTex Meme" width="50%">
</p>

## TL;DR (Quick Start)

1. **Click "Use this template"** on GitHub to create your own repository.
2. **Open the environment:**

   ### Local Setup (Standard)

   **System requirements** — You need a modern LaTeX distribution (TeX Live 2020+ or MiKTeX) with:

   | Component     | Minimum version | Notes                                                  |
   | ------------- | --------------- | ------------------------------------------------------ |
   | **TeX Live**  | 2020            | Any recent LaTeX distribution                          |
   | **latexmk**   | 4.70            | Automates compilation passes                           |
   | **biber**     | 2.17            | Required for bibliography processing with `biblatex`   |
   | **biblatex**  | 3.15            | `numeric` citation style                               |
   | **csquotes**  | —               | Recommended by `biblatex`                              |

   **Quick install per platform:**

   | Platform          | Command                                                                                            |
   | ----------------- | -------------------------------------------------------------------------------------------------- |
   | **Ubuntu/Debian** | `sudo apt install texlive-latex-recommended texlive-latex-extra texlive-bibtex-extra biber latexmk`|
   | **Fedora**        | `sudo dnf install texlive-scheme-medium texlive-biblatex texlive-csquotes biber latexmk`           |
   | **macOS**         | `brew install --cask mactex` (or `brew install --cask basictex` + `tlmgr install` everything)       |
   | **Windows**       | Install [MiKTeX](https://miktex.org/) or [TeX Live](https://tug.org/texlive/)                      |

   **VS Code Extensions (system-wide):**

   | Extension           | ID                           | Purpose                                        |
   | ------------------- | ---------------------------- | ---------------------------------------------- |
   | **LaTeX Workshop**  | `James-Yu.latex-workshop`    | Auto compilation, PDF preview, SyncTeX         |
   | **Live Share**      | `ms-vsliveshare.vsliveshare` | Real-time collaboration with multiple people   |

   Then:

   ```bash
   git clone <repository-url>
   code <project-folder>
   ```

   Open `main.tex` and start writing. Every **save (Ctrl + S)** compiles automatically!

   ### Or use GitHub Codespace
   - **From VS Code:** Install the _GitHub Codespaces_ extension, `Ctrl+Shift+P` > **Create New Codespace**. (Low latency)
   - **From browser:** Open the repo on GitHub > `Code` > `Codespaces` > **Create codespace**. (Zero setup)

3. **Wait** for the environment to load.
4. Find the PDF in the `build/` folder.

---

## Working Together (Real-Time Collaboration)

TeamTex supports collaborative writing through **Live Share** (`ms-vsliveshare.vsliveshare`), pre-configured in the container.

1. Open the project in VS Code.
2. Click the **Live Share** icon in the sidebar (or `Ctrl+Shift+P` > **Live Share: Start Collaboration Session**).
3. Share the link with your collaborators — they can edit the `.tex` files and see the compilation in real time.

> **PDF Sync:** All participants see the same compiled PDF by opening `build/main.pdf` with the built-in LaTeX Workshop viewer.

---

## Workspace Directory Handling

Whether you are using GitHub Codespaces or Local Dev Containers, your entire repository is automatically mapped inside the container to the `/workspace` directory.

Any files, scripts, images, or custom sub-folders (e.g., `src/`, `chapters/`, `assets/`) you add to your project folder alongside `main.tex` are instantly loaded, fully accessible by LaTeX during compilation, and synced with your local machine/GitHub.

---

## More Usage Details

> [!IMPORTANT]
> **Check the [More Usage Details](docs/usage-details.md) guide** for essential information on **Templates**, **Copilot**, **Troubleshooting**, and **Custom Extensions**. This is where you'll find everything you need for a professional setup.

---

## Table of Contents

1. [Compiling the Project](#compiling-the-project)
2. [Exporting (ZIP & PDF)](#exporting-zip--pdf)
3. [Detailed Guides](#detailed-guides)
   - [Work Environments](docs/environments.md)
   - [Git Workflow & Best Practices](docs/git-workflow.md)
   - [More Usage Details](docs/usage-details.md)

---

## Compiling the Project

The project is specifically configured to keep the root directory clean by routing all files into the `build/` directory.

### Option A: VS Code / Codespace (Recommended)

1. Open `main.tex`.
2. Saving (Ctrl + S) triggers automatic compilation.
3. Use the TeX sidebar icon for manual builds or to view the PDF.

### Option B: Terminal

If you prefer the command line, use `latexmk` directly:

```bash
# Full Compile (handles bibliography, multiple passes automatically)
latexmk -pdf -outdir=build main.tex

# Clean
latexmk -C -outdir=build
rm -rf build/
```

---

## Exporting (ZIP & PDF)

### Download PDF

- **Codespaces / Remote:** Right-click `main.pdf` in the `build/` folder > **Download**.
- **Local Dev Container:** The PDF is already in your local `build/` folder.

### Download Source (ZIP)

To get a clean archive of your source code (excluding build files and Git history):

- **Run `./export_source.sh`** in the terminal.
- **Based on your environment:**
  - **Codespaces / Remote:** Right-click the generated `teamtex_source.zip` > **Download**.
  - **Local Dev Container:** The ZIP is already in your project folder.

---

## Detailed Guides

| Guide                                           | Description                                                 |
| :---------------------------------------------- | :---------------------------------------------------------- |
| [**Work Environments**](docs/environments.md)   | How to setup Codespaces, Local Docker, or Native LaTeX.     |
| [**Git Workflow**](docs/git-workflow.md)        | Divergent branches, Codespace persistence, and branching.   |
| [**More Usage Details**](docs/usage-details.md) | Templates, Copilot, Troubleshooting, and custom extensions. |

> [!TIP]
> **Don't stop at the Quick Start!** We highly recommend reading through all the detailed guides above to fully master the TeamTex environment and its collaborative features.

---
