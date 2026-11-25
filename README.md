# Visualisation Group Work

A group-work exercise for practising data visualisation in Python. Working in small groups, you recreate the same chart in several plotting libraries so you can compare their syntax and results side by side. The datasets cover Seattle weather and US airport locations. The full brief, including group assignments, lives in the [task file](1-visualisation-task.md).

## Learning Objectives

By the end of this repository, you should be able to:

- Create scatter, line, and bar charts using Matplotlib, Seaborn, and Plotly.
- Build interactive geographical maps of point data with Plotly.
- Apply the principles of a good plot (clear title, axis labels with units, readable legends and text) to every figure.
- Compare the three libraries' syntax and trade-offs to pick the right tool for a given chart.

## Learning Path

Start with the task file to find your group's chart and dataset, then build your plots in the template notebook.

| File / Folder | Description |
|---|---|
| [**Visualisation Task**](1-visualisation-task.md) | The brief: group assignments, datasets, and what makes a plot good. |
| [**Visualisation Template**](2-visualisation-template.ipynb) | Starter notebook with one section per library (Matplotlib, Seaborn, Plotly). Add your plots here. |

### Additional Folders and Files

| File / Folder | Description |
|---|---|
| [**Data**](data_group_work/) | Seattle weather and US airport datasets used in the exercise. |
| [**Assets**](assets/) | Example plot referenced in the task brief. |
| [**Solutions**](solutions/) | Reference solutions (added later in the course). |
| [**pyproject.toml**](pyproject.toml) | Project configuration and dependencies. |
| [**uv.lock**](uv.lock) | Pinned dependency versions. |

## Setup

> [!NOTE]
> Throughout these steps, text in angle brackets like `<repo-name>` is a **placeholder**. Replace it, including the `< >` brackets, with your own value. For example, `cd <repo-name>` becomes `cd ds-visualisation-group-work`.

### 1. Create the Repository from the Template

Click **Use this template** on GitHub.

When creating the repository:

- Set yourself as the **Owner**
- Choose a repository name
- Disable **Include all branches**
- Click **Create repository**

> [!IMPORTANT]
> This is group work. Only **one person** should complete this step, then add the others as collaborators in the next step.

---

### 2. Add Collaborators

1. Open the repository on GitHub
2. Go to **Settings → Collaborators**
3. Add your teammates as collaborators
4. Share the repository link with your team

Teammates should accept the invitation before continuing.

---

### 3. Clone the Repository

Copy the SSH URL from the **Code** button on GitHub, then run:

```bash
git clone <copied-ssh-url>
```

The copied SSH URL will look like `git@github.com:<your-username>/<repo-name>.git`.

---

### 4. Move into the Project Folder and Install Dependencies

This installs all dependencies and creates a virtual environment in `.venv/`.

```bash
cd <repo-name>
uv sync
```

---

### 5. Open the Notebook

> [!NOTE]
> Open VS Code from the project root so it automatically detects the environment created by `uv sync`.

Launch VS Code in the project root folder:

```bash
code .
```

Then open `2-visualisation-template.ipynb` and select the Python environment created by `uv sync` as the kernel.

## My work

- **Done solo**: this is group work, but I worked through it alone, so there was no team and no other group to swap notebooks with.
- **Group 2 (line plot, Seattle weather)** in [`2-visualisation-template.ipynb`](2-visualisation-template.ipynb): average daily maximum and minimum temperature per calendar month, built in Matplotlib, Seaborn and Plotly with the same colour-blind safe colours (Okabe-Ito blue and vermillion). Plus a Seaborn version that averages the raw days itself and draws 95 % confidence bands, and a comparison table of the three libraries. My own September 2026 draft was the start; its missing data steps (`monthly_long`, the data import) are now in place, so the notebook runs top to bottom.
- **Solo extension, the other groups' charts**: Group 1 scatter (warm nights come with warm days, r = 0.88), Group 3 bar (rain per month: November wettest, July driest) plus a bar chart that shows the `weather` labels changed over the years (use `precipitation`, not the label), Group 4 maps (Plotly dot map and airports-per-state choropleth, plus a Matplotlib x/y version for comparison).
- Plotly charts are stored twice: interactive in Jupyter and as a PNG copy that GitHub can show (`pio.renderers.default = "plotly_mimetype+png"`, needs `kaleido`, added to `pyproject.toml`).
- Claude finished the notebook in a delegated pass on 2026-11-26; owner review pending.

## References & Further Reading

- [Matplotlib tutorials](https://matplotlib.org/stable/tutorials/index.html): Official guides from the basics to advanced plotting.
- [Seaborn user guide and tutorial](https://seaborn.pydata.org/tutorial.html): How to build statistical graphics with seaborn.
- [Plotly scatter plots on maps](https://plotly.com/python/scatter-plots-on-maps/): Official guide to the geographical maps used in this exercise.
- [From Data to Viz](https://www.data-to-viz.com/): A decision tree for choosing the right chart type for your data.
- [The Python Graph Gallery](https://www.python-graph-gallery.com/): Hundreds of worked chart examples with copy-ready code.
