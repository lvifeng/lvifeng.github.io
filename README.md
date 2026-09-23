# lvifeng.github.io

## What this repository is

My Quarto website, published with GitHub <https://github.com/lvifeng/lvifeng.github.io> at <https://lvifeng.github.io/>.

## What to install first

Install these first (with the versions I used):

- [Quarto](https://quarto.org/docs/get-started/) 1.10.18
- [uv](https://docs.astral.sh/uv/getting-started/installation/) 0.12.5 (uv installs the pinned Python version automatically)
- [R](https://cran.r-project.org/) 4.6.1 (`renv` installs itself on first run)

## Steps to follow to build site

In a terminal, clone the repository and install the Python packages using `uv sync` (after git clone, make sure to `cd` to the "lvifeng.github.io" folder):

```bash
git clone https://github.com/lvifeng/lvifeng.github.io.git
cd lvifeng.github.io
uv sync
```

Then in the same root file, install the R packages. Start R console by calling `R` in the terminal and enter `renv::restore()`, then quit using `q()`:

```bash
R
```

```r
renv::restore()
q()
```

When asked to save the workspace, answer `n`.

Back in the terminal, build the site:

```bash
uv run quarto render
```

## Where the built site lands and how to open locally

The built site is written to `docs/`.

To view it, double-click the `docs/index.html` file 
in your file browser.

## Where the data comes from

Both posts use the [Palmer Penguins](https://allisonhorst.github.io/palmerpenguins/) data
(Palmer Station Antarctica LTER, CC-0 licence),
which is inside the `palmerpenguins` Python and R packages.

The build does not need the network to fetch the data, as it is installed along with the packages when `uv sync` and `renv::restore()`.
