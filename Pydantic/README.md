
# 📘 Pydantic Practice with Python

This repository contains a beginner-friendly Jupyter notebook that demonstrates how to use **Pydantic** for data validation in Python. It includes multiple examples using `BaseModel`, `Optional`, `List`, `Field`, and nested models, as well as how to handle common validation errors.

## 🔍 What You'll Learn

- How to define structured models using `pydantic.BaseModel`
- Using `Optional` and default values
- Type validation with `List`, `str`, `int`, and `float`
- Custom constraints using `Field`
- Working with nested models
- How to catch and understand `ValidationError`

## 📂 Files

- `pydentic.ipynb` – The main notebook that includes:
  - Valid model creation examples ✅
  - Invalid input examples ❌ (with errors shown)
  - Use of `try/except` to handle validation errors gracefully

## ✅ Correct Example

```python
from pydantic import BaseModel

class Person(BaseModel):
    name: str
    age: int
    city: str

person = Person(name="muhammed", age=23, city="calicut")
print(person)
```

## ❌ Common Mistake Example

```python
person = Person(name="muhammed", age=23, city=3)  # ❌ City must be a string!
```

**Error:**
```
ValidationError: 1 validation error for Person
city
  Input should be a valid string [type=string_type, input_value=3, input_type=int]
```

## ⚠️ Lessons from Mistakes

- Always match the expected type in your models (e.g., don't pass an `int` where a `str` is expected).
- When using `List[str]`, ensure all elements are strings.
- Use `try/except` blocks to catch `ValidationError` and handle invalid data cleanly.

## 🛠 Requirements

- Python 3.7+
- `pydantic>=2.0`
- Jupyter Notebook (for `.ipynb`)

```bash
pip install pydantic jupyter
```

## 🚀 Running the Notebook

```bash
jupyter notebook pydentic.ipynb
```

## 📌 Note

This project is a personal practice notebook for learning Pydantic. Mistakes were intentionally left in for educational purposes.

## 📬 Contact

Feel free to reach out via [GitHub Issues](https://github.com/YOUR_USERNAME/YOUR_REPO/issues) if you have questions or suggestions.
