---
description: How to upload cefpythonx to PyPI
---

# Uploading cefpythonx to PyPI (Manual Method)

> [!NOTE]
> We have set up **GitHub Actions** to do this automatically. See `.github/workflows/python-publish.yml`.
> Use these instructions only if you need to build and upload manually from your local machine.

## Prerequisites
1.  **Build the distribution packages**:
    Run `python tools/build_distrib.py 0.1 --allow-partial` to create the wheel and source distributions in `build/distrib/`.

2.  **Install Twine**:
    ```bash
    pip install twine
    ```

## Upload Steps

1.  **Check the packages**:
    Verify that the `.whl` and `.zip` (or `.tar.gz`) files are in `build/distrib/`.

2.  **Upload to TestPyPI (Optional but Recommended)**:
    ```bash
    python -m twine upload --repository testpypi build/distrib/*
    ```

3.  **Upload to PyPI**:
    ```bash
    python -m twine upload build/distrib/*
    ```

## Verification
- Visit [https://pypi.org/project/cefpythonx/](https://pypi.org/project/cefpythonx/) to verify the release.
