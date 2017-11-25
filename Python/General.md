<div dir=rtl>بنام خدا</div>

- Update All Python Packages:
```python
  pip freeze --local | grep -v '^\-e' | cut -d = -f 1  | xargs -n1 pip install -U
```
- Json Validating
```bash
  cat Json.File | python -m json.tool
```
