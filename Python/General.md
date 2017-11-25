<div dir=rtl>بنام خدا</div>

- Update All Python Packages:
```vim
  pip freeze --local | grep -v '^\-e' | cut -d = -f 1  | xargs -n1 pip install -U
```
- Json Validating
```vim
  cat Json.File | python -m json.tool
```
