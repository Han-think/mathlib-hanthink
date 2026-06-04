# mathlib-hanthink

`mathlib-hanthink` is a small class-based Python math utility package created as a packaging, testing, versioning, and PyPI distribution practice project.

This project is intentionally simple in mathematical scope, but it is structured to demonstrate a complete Python package release workflow:

* source layout packaging
* class-based module design
* pytest-based verification
* semantic versioning
* PyPI distribution
* Git commit and tag history
* incremental feature releases

---

## Beginner Explanation

This project is a small Python library.

A Python library is a group of Python files that other people can install and use.

For example:

```bash
pip install mathlib-hanthink
```

After installing it, someone can use it in Python:

```python
from mathlib_hanthink.arithmetic import Arithmetic

calc = Arithmetic(10, 5)
print(calc.add())
```

This project was made to practice how Python code becomes an installable package.

The main goal is not to create a powerful math engine.
The main goal is to understand the full package workflow:

```text
write code
→ write tests
→ build package
→ upload to PyPI
→ install package
→ use package from Python
```

---

## Expert-Level Explanation

`mathlib-hanthink` is a deliberately minimal, didactic Python package that demonstrates a release-oriented packaging workflow using the `src/` layout, PEP 621-style project metadata in `pyproject.toml`, isolated test execution through `pytest`, and distributable artifacts built as both source distribution and wheel.

The package is structured around small class-based abstractions rather than broad numerical generality. This is intentional. The objective is not to compete with mature numerical libraries such as NumPy, SciPy, SymPy, or pandas. Instead, this repository focuses on the operational mechanics of Python package lifecycle management:

* separating importable source code from project root files
* maintaining package metadata in `pyproject.toml`
* incrementally introducing features across semantic versions
* validating each release with automated tests
* generating reproducible distribution artifacts
* publishing versioned artifacts to PyPI
* preserving release history through Git commits and tags

In practical terms, this repository is a packaging exercise disguised as a math utility library.

The math is simple.
The workflow is the actual subject.

---

## Versioned Release Roadmap

This repository is developed as a sequence of incremental releases.

### v0.1.0 - Arithmetic

The first release introduces the `Arithmetic` class.

Supported operations:

* addition
* subtraction
* multiplication
* division
* division-by-zero error handling

Example:

```python
from mathlib_hanthink.arithmetic import Arithmetic

calc = Arithmetic(10, 5)

print(calc.add())
print(calc.subtract())
print(calc.multiply())
print(calc.divide())
```

---

### v0.2.0 - Geometric Sequence

The second release adds the `GeometricSequence` class.

Supported operations:

* generate a geometric sequence
* calculate the nth term
* calculate the sum of the sequence
* handle ratio-one sequence summation

Example:

```python
from mathlib_hanthink.geometric import GeometricSequence

seq = GeometricSequence(2, 3, 4)

print(seq.generate())
print(seq.nth_term(3))
print(seq.sum())
```

---

### v0.3.0 - Trigonometry

The third release adds the `Trigonometry` class.

Supported operations:

* sine
* cosine
* tangent
* tangent undefined-case handling

Example:

```python
from mathlib_hanthink.trigonometry import Trigonometry

trig = Trigonometry(30)

print(trig.sin())
print(trig.cos())
print(trig.tan())
```

---

## Installation

Install from PyPI:

```bash
pip install mathlib-hanthink
```

Install a specific version:

```bash
pip install mathlib-hanthink==0.1.0
pip install mathlib-hanthink==0.2.0
pip install mathlib-hanthink==0.3.0
```

---

## Full Usage Example

```python
from mathlib_hanthink.arithmetic import Arithmetic
from mathlib_hanthink.geometric import GeometricSequence
from mathlib_hanthink.trigonometry import Trigonometry

calc = Arithmetic(10, 5)

print(calc.add())
print(calc.subtract())
print(calc.multiply())
print(calc.divide())

seq = GeometricSequence(2, 3, 4)

print(seq.generate())
print(seq.nth_term(3))
print(seq.sum())

trig = Trigonometry(30)

print(trig.sin())
print(trig.cos())
print(trig.tan())
```

---

## Project Structure

```text
mathlib-hanthink/
├── src/
│   └── mathlib_hanthink/
│       ├── __init__.py
│       ├── arithmetic.py
│       ├── geometric.py
│       └── trigonometry.py
├── tests/
│   ├── test_arithmetic.py
│   ├── test_geometric.py
│   └── test_trigonometry.py
├── pyproject.toml
├── README.md
├── CHANGELOG.md
├── LICENSE
└── uv.lock
```

---

## Development

Install development dependencies:

```bash
uv sync --group dev
```

Run tests:

```bash
uv run pytest tests/ -v
```

Build the package:

```bash
uv build
```

Expected build artifacts:

```text
dist/
├── mathlib_hanthink-<version>.tar.gz
└── mathlib_hanthink-<version>-py3-none-any.whl
```

---

## Testing Philosophy

The tests are intentionally small and direct.

They verify that each public class behaves as expected for its basic use cases.

The test suite checks:

* arithmetic correctness
* division-by-zero error handling
* geometric sequence generation
* geometric nth-term calculation
* geometric sequence summation
* trigonometric function output
* undefined tangent cases

This is not a mathematically exhaustive test suite.
It is a packaging-oriented verification suite.

Its job is to prove that the package can be installed, imported, tested, built, and released correctly.

---

## What This Project Is Not

This project is not:

* a replacement for NumPy
* a replacement for SciPy
* a symbolic algebra system
* a high-performance numerical library
* a production-grade scientific computing package

This project is:

* a Python packaging practice project
* a small installable math utility package
* a versioned release workflow exercise
* a PyPI distribution practice repository
* a record of incremental package development

---

## Release Workflow

The release workflow used in this project is:

```text
modify source code
→ update package version
→ run pytest
→ build package artifacts
→ commit changes
→ create Git tag
→ push to GitHub
→ upload to PyPI
→ verify installation
```

Example:

```bash
uv run pytest tests/ -v
uv build
git add .
git commit -m "v0.3.0 Add Trigonometry class"
git tag v0.3.0
git push origin main
git push origin v0.3.0
uv run twine upload dist/*
```

---

## Why This Repository Exists

This repository exists to make the invisible part of Python development visible.

Writing a function is easy.

Releasing a package properly requires more structure:

* metadata
* tests
* build configuration
* version numbers
* distribution files
* release notes
* Git history
* PyPI publishing

This repository documents that process in a small, inspectable form.

The code is small on purpose.
The workflow is the point.
