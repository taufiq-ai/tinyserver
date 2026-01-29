# TinyServer

**Zero-dependency HTTP API server built on Python's stdlib.** Simple, fast, pure Python.


## Quick Setup
```bash
git clone https://github.com/taufiq-ai/nanoserver.git
cd nanoserver
```

## Process of new release

### Clean old builds and create new
```sh
rm -rf dist/ build/ *.egg-info

# Build new version
python -m build
```

This creates:  
- `dist/nanoserver-0.1.1.tar.gz`
- `dist/nanoserver-0.1.1-py3-none-any.whl`

### Upload to PyPI
```sh
# Upload to PyPI
python -m twine upload dist/*

# It will ask for:
# Username: __token__
# Password: pypi-xxxxx (your API token)
```

### Verify
```sh
# Check on PyPI
# https://pypi.org/project/nanoserver/

# Test install
pip install --upgrade nanoserver

# Verify version
python -c "import nanoserver; print(nanoserver.__version__)"
```


## Tips for PyPI Tokens

Use `.pypirc` for easier uploads.  
Create `~/.pypirc`:
```
[testpypi]
  username = __token__
  password = pypi-YOUR_TESTPYPI_TOKEN_HERE

[pypi]
  username = __token__
  password = pypi-YOUR_PYPI_TOKEN_HERE
```

## Meaning behind version numbering:
- 0.1.0 → 0.1.1 (bug fixes)
- 0.1.0 → 0.2.0 (new features)
- 0.1.0 → 1.0.0 (major changes/breaking)

## Links
- Issues: https://github.com/taufiq-ai/nanoserver/issues  
- PyPI: https://pypi.org/project/nanoserver/  
- Test PyPI: https://test.pypi.org/project/nanoserver/  
- PyPI Buid Guidelines: https://packaging.python.org/en/latest/tutorials/packaging-projects/  
- PyPI Token Generation: https://pypi.org/manage/account/token/  