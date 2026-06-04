# mathlib-hanthink

A simple class-based Python math utility package for packaging and PyPI distribution practice.

## Features

- Basic arithmetic operations
- Geometric sequence utilities
- Trigonometry utilities
- Pytest-based tests
- PyPI-ready package structure

## Installation

```bash
pip install mathlib-hanthink
```

## Usage

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

## Development

```bash
uv sync --group dev
uv run pytest -v
uv build
```

## Project Structure

```text
mathlib-hanthink/
├── src/
│   └── mathlib_hanthink/
├── tests/
├── pyproject.toml
├── README.md
├── CHANGELOG.md
└── LICENSE
```

## Purpose

This project was created to practice Python package structure, testing, building, and PyPI distribution.
