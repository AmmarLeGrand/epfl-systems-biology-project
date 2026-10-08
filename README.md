# Systems Biology Project

Just a quick guide to set up the environment and use Git.

## Setup

First, clone the repo:

```bash
git clone https://github.com/AmmarLeGrand/epfl-systems-biology-project.git
cd epfl-systems-biology-project
```

Make sure you have Conda installed, then create the environment using the `environment.yml` file:

```bash
conda env create -f environment.yml
conda activate sys_bio-env
```

This should install all the packages we need.

In VS Code, open the project folder and select `sys_bio-env` as the Python/Jupyter kernel.

You only need to create the environment once. Next time, just activate it.

If we add new packages later:

```bash
conda env update -f environment.yml --prune
```

## Git basics

Before starting something, get the latest version:

```bash
git switch main
git pull origin main
```

Create your own branch to work on:

```bash
git switch -c your-branch-name
```

Once you've made some changes:

```bash
git status
git add .
git commit -m "what you changed"
git push -u origin your-branch-name
```

After the first push, you can just use `git push`.

When you're done, go to GitHub and open a **pull request** to merge your branch into `main`.

## A few things

- Try not to work directly on `main`.
- Pull the latest changes before starting.
- Avoid editing the same notebook at the same time (Git doesn't handle notebook conflicts very well).
- If you install a new package that we need, add it to `environment.yml`.
- Keep the data in `data/` and notebooks in `notebooks/`.

That's pretty much it :)