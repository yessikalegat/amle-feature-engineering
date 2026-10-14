# Feature Engineering

A model can only learn from what its features show it. **Feature engineering** turns raw data into features a model can use: it fills in missing values, turns categories into numbers, brings numbers onto similar ranges and creates new features. This repository builds on W3D2, where you scaled features and created polynomial terms. You will:

- fill in missing values, encode categories, bin and scale numbers, and create new features with scikit-learn transformers
- combine these steps with `ColumnTransformer` and `Pipeline` into one reproducible workflow
- apply everything to a real dataset, comparing feature engineering versions on a validation set

Cross-validation in W3D4 then makes that comparison more reliable, and in Friday's King County housing project you apply these techniques to predict house prices. Before starting the notebooks, read the [machine learning workflow notes](machine_learning_workflow.md).

## Learning Objectives

By the end of this repository, you should be able to:

- Impute missing values with `SimpleImputer`, fitted on the training data only, and apply the same fitted transformations to the test data.
- Encode nominal features with `OneHotEncoder` and ordinal features with `OrdinalEncoder`.
- Discretise a numeric feature into bins, and scale and log-transform numeric features.
- Create polynomial and interaction terms with `PolynomialFeatures`, and new features by hand, such as a ratio of two columns.
- Build a `ColumnTransformer` and a `Pipeline` that combine the preprocessing with a linear regression model.
- Compare feature engineering versions on a validation set, and score the chosen version once on a test set.

## Learning Path

Work through the notebooks in this order:

| File / Folder | Description |
|---|---|
| [**01 - Feature Engineering Basics**](01_feature_engineering_basics.ipynb) | Imputation, categorical encoding, binning, scaling and feature expansion on the penguin data. |
| [**02 - Exercise: Feature Engineering Basics**](02_exercise_feature_engineering_basics.ipynb) | Practise the basic tools step by step on a small snowman dataset, then transform a test set. |
| [**03 - Column Transformers and Pipelines**](03_pipelines.ipynb) | Combine the preprocessing steps with `ColumnTransformer` and `Pipeline`, and train a model inside a pipeline. |
| [**04 - Exercise: Column Transformers and Pipelines**](04_exercise_pipelines.ipynb) | Rebuild the snowman preprocessing as a `ColumnTransformer` with pipelines, then add a linear regression model (bonus). |
| [**05 - Exercise: Feature Engineering on a Real Dataset**](05_exercise_diamond_prices.ipynb) | Predict the price of almost 54,000 diamonds: split into training, validation and test sets, compare ordinal and one-hot encoding and a log transform on the validation set, and score the chosen version on the test set. Two bonuses: polynomial terms, feature selection with correlations, group-wise removal and RFE, and a volume feature created by hand. |

### Additional Folders and Files

| File / Folder | Description |
|---|---|
| [**Machine Learning Workflow**](machine_learning_workflow.md) | Background reading on where feature engineering fits in the machine learning workflow. |
| [**Data**](data/) | The [Palmer Penguins](https://allisonhorst.github.io/palmerpenguins/) dataset used in the lesson notebooks, and the [diamonds](https://ggplot2.tidyverse.org/reference/diamonds.html) dataset from the ggplot2 R package used in exercise 05. |
| [**Assets**](assets/) | Images used in the notebooks, including the machine learning workflow diagram used in exercise 05. |
| [**Solutions**](solutions/) | Worked solutions for the exercise notebooks. |
| [**pyproject.toml**](pyproject.toml) | Project configuration and dependencies. |
| [**uv.lock**](uv.lock) | Dependency lock file. |

## Setup

> [!NOTE]
> Throughout these steps, text in angle brackets like `<repo-name>` is a
> **placeholder**. Replace it, including the `< >` brackets, with your own
> value. For example, `cd <repo-name>` becomes `cd amle-feature-engineering`.

### 1. Create the Repository from the Template

Click **Use this template** on GitHub.

When creating the repository:

- Set yourself as the **Owner**
- Choose a repository name
- Disable **Include all branches**
- Click **Create repository**

> [!IMPORTANT]
> If you are working in pairs or groups, only **one person** should complete this step.

---

### 2. Add Collaborators (Pairs/Groups Only)

If working with teammates:

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

### 5. Open the Notebooks

> [!NOTE]
> Make sure you open VS Code from the project root so it automatically detects the environment created by `uv sync`.

Launch VS Code in the project root folder:

```bash
code .
```

Then open a notebook and select the Python environment created by `uv sync` as the kernel.

## References & Further Reading

- [**Scikit-learn: Preprocessing data**](https://scikit-learn.org/stable/modules/preprocessing.html): Official reference for imputation, encoding, scaling and discretisation.
- [**Scikit-learn: Pipelines and composite estimators**](https://scikit-learn.org/stable/modules/compose.html): How `ColumnTransformer` and `Pipeline` fit together.
- [**Scikit-learn: Compare the effect of different scalers**](https://scikit-learn.org/stable/auto_examples/preprocessing/plot_all_scaling.html): A visual comparison of scaling methods on real data.
- [**Discover Feature Engineering**](https://machinelearningmastery.com/discover-feature-engineering-how-to-engineer-features-and-how-to-get-good-at-it/): A practical overview of feature engineering in applied projects.
