# Instructor Guide: EE380 Course Website

This website is built with **Quarto**. It uses **GitHub Pages** for hosting and **Pyodide** for interactive Python simulations.

## 1. Initial Setup

### Create the Repository
1.  Create a new repository on GitHub (e.g., `ee380-website`).
2.  Clone this folder to your machine.
3.  Push this initial code to the `main` branch.

### Install Tools
1.  **Install Quarto:** Download from [quarto.org](https://quarto.org/).
2.  **VS Code:** Recommended editor. Install the "Quarto" extension.
3.  **Install Pyodide Extension:** Open a terminal in this folder and run:
    ```bash
    quarto add quarto-ext/shinylive
    # OR for standard pyodide
    quarto add coatless-quarto/pyodide
    ```
    *(Note: The current template assumes standard code blocks initially. To use the interactive features, you must install the extension.)*

## 2. Weekly Workflow

### Updating the Schedule
1.  Open `calendar.qmd`.
2.  Add new rows to the table for the upcoming week.
3.  Link slides (put PDF files in a `slides/` folder if you like, or link externally).

### Posting Homework
1.  Open `homework.qmd`.
2.  Add a new row to the table.
3.  Link the PDF assignment.

### Publishing Changes
To publish, you just need to push to GitHub. The Setup is already configured (see `.github/workflows/publish.yml`).

```bash
git add .
git commit -m "Update week 3 schedule"
git push
```
Within nearly 60 seconds, your site at `https://<username>.github.io/<repo>` will update.

## 3. Adding Interactive Simulations

Once the Pyodide extension is installed, you can add interactive cells like this:

````markdown
```{pyodide-python}
import matplotlib.pyplot as plt
import numpy as np
x = np.linspace(0, 10, 100)
plt.plot(x, np.sin(x))
plt.show()
```
````

This will render as an interactive, editable, regular Python cell in the student's browser.
