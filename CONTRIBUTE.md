# Contributing to Iris API

Thank you for your interest in contributing to **Iris API** 🎉
We welcome all kinds of contributions — from bug reports and feature suggestions to code improvements and documentation updates.

---

## 🧑‍💻 Development

### Setup

1. Fork the repository and clone your fork locally.
2. Create a new branch from `main` for your changes.

```bash
git checkout -b feature/your-feature-name
```

### Translations

If you want to add some translations, use the following commands to generate/update the i18n files.

**These commands must be run in the `docs` folder.**

```bash
make gettext
sphinx-intl update -p build/gettext -l en -l fr
```

> You can add a `-l` for each language you want to add

### Validations

- Create a venv : `python -m venv myenv`
- Activate it : `myenv\Scripts\activate` or `source myenv/bin/activate`
- Install the dependencies : `pip install -r requirements.txt`
- Build the docs

```bash
sphinx-build -b html -D language=en docs/source docs/build
sphinx-build -b html -D language=fr docs/source docs/build/fr
```

- Start the server : `python -m http.server 8000`
- Then validate the logs if everything is fine and if all the updated pages are working correctly

---

## 🧾 Code Guidelines

* Write **clean, well-documented code/documentation**.
* Follow existing documentation style and structure.

---

## 🚀 Submitting Changes

1. Push your branch to your fork.
2. Open a **Pull Request (PR)** against the `main` branch.
3. In your PR description:

    * Explain **why** you’re making the change.
    * Describe **what** it does.
    * Mention any relevant **issues** or **discussions**.

The maintainers will review your PR and may request changes or improvements before merging.

---

## 🧩 Versioning & Releases

* The current version is tracked in **`version.yaml`**.
* All version updates and notable changes must be documented in **`CHANGELOG.md`**.
* Follow [Semantic Versioning](https://semver.org/) when incrementing versions.

---

## 🙌 Acknowledgment

Once your contribution is merged, please **add your name** to the list of contributors in the `README.md` file under the “Contributors” section.
We appreciate your efforts and want to give you proper credit for your work.