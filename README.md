# Ship 1 — Python Track

Build on your Ship 0 skills by adding new features to your Ship Log CLI app.

## Why you're doing this

* To practice working with dates and times in Python
* To get more comfortable with Git commands
* To learn how to add features to existing code
* To understand how to modify and extend a project

## How this assignment works

This template contains **TODO comments** throughout the code that you need to implement:

* Look for `# TODO:` comments in the source files
* Each TODO includes hints about what to implement
* Start with the Baseline requirements, then move to Hard Mode
* Run `pytest -q` to test your implementations
* The tests will fail until you implement the required functions

---

## Get the Code

Start from where you left off in Ship 0. Make sure you're on your personal branch:

```bash
# If you're starting fresh:
git clone <your-ship0-repo-url>
cd ship0-template-python
git checkout <firstname-lastname>
```

**OR** if you're using this as a template:

```bash
# Clone this template repository
git clone <this-repo-url>
cd ship1-template-python
git checkout -b <firstname-lastname>
```

---

## What is a virtual environment (venv), really?

A **virtual environment** is a self-contained folder that holds its own Python interpreter and installed packages. It keeps your project's dependencies isolated from the rest of your machine so one project's install doesn't break another's.

* Creating a venv: `python3 -m venv .venv` creates a `.venv/` folder in your repo.
* Activating it: `source .venv/bin/activate` (macOS/Linux) or `.\.venv\Scripts\activate` (Windows).
* Why activate? So `python` and `pip` point **inside** the venv. Confirm with `which python` (macOS/Linux) or `where python` (Windows).

When you're done, deactivate with `deactivate` or just close the terminal. You can delete a venv by removing the `.venv/` folder and recreating it later.

---

## What is `pip`?

`pip` is Python's package installer. It grabs packages from the Python Package Index (PyPI).

* Upgrade it inside your venv: `python -m pip install --upgrade pip`
* Install from a list: `pip install -r requirements.txt`

We use **NumPy** for a tiny stat calculation and **pytest** for tests.

---

## What does `python -m` do?

The `-m` flag runs a **module** by name (like `ship0`) instead of a file path. It tells Python to treat the current directory as a package, look up `ship0/__main__.py`, and execute it. This is how you'll run your CLI: `python -m ship0`.

---

## Baseline (Required) — Add Entry with Timestamp

Add a timestamp feature to your Ship Log entries.

**What to implement:**

1. Modify the `add` command to automatically include a timestamp
2. Format the timestamp nicely (e.g., "2024-01-15 14:30:25")
3. Update the `list` command to show timestamps

**Files to modify:**

* `src/ship1/storage.py` - Update the add_entry function (look for TODO comments)
* `src/ship1/cli.py` - Make sure the timestamp shows when listing (look for TODO comments)

**Implementation hints:**
- Look for `# TODO:` comments in the code
- The `add_entry` function needs to create timestamps using `time.strftime()`
- The `list` command needs to show numbered entries with timestamps

**Git practice:**

```bash
# Make your changes, then:
git add -A
git commit -m "Ship 1: Added timestamp to entries"
git push origin <firstname-lastname>
```

**Pass (Baseline) if:**

* `python -m ship0 add "Your message"` includes a timestamp
* `python -m ship0 list` shows entries with timestamps
* You've made at least one commit with a clear message

---

## Hard Mode (Optional) — Delete and Search Features

Add more advanced features to your Ship Log.

**Delete by index/ID:**

Implement a delete command that removes entries by their position or ID:

```bash
python -m ship1 delete 3  # Deletes the third entry
```

**Search/Filter:**

Implement a search command that finds entries containing specific text:

```bash
python -m ship1 search "python"  # Finds all entries mentioning "python"
```

**Files to modify:**

* `src/ship1/storage.py` - Implement delete_entry and search_entries functions (look for TODO comments)
* `src/ship1/cli.py` - Implement delete and search command handlers (look for TODO comments)

**Implementation hints:**
- Look for `# TODO:` comments in the code
- `delete_entry(index)` should validate the index and remove the entry
- `search_entries(query)` should do case-insensitive text matching
- Both functions should return appropriate values for the CLI to handle

---

## Testing Your Work

Run the existing tests to make sure you didn't break anything:

```bash
pytest -q
```

Test your new features manually:

```bash
python -m ship1 add "Test entry with timestamp"
python -m ship1 list
# For hard mode:
python -m ship1 delete 1
python -m ship1 search "test"
```

---

## Troubleshooting

* **Broken existing features?** Run `pytest -q` to check
* **Git issues?** Make sure you're on your personal branch
* **Import errors?** Ensure your venv is active

---

## What to submit

* Repo URL with your Ship 1 changes
* Whether you did Baseline or Hard Mode
* Time spent + any challenges faced

Submit [here](https://forms.gle/uoAQkv48QDkEM81m9)

---

Do you want me to also **rewrite the README file for the repo itself** in this style so it's copy-paste ready for GitHub?
