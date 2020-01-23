# Useful python snippet

## unzip

```python
import sys
from zipfile import PyZipFile
with PyZipFile("file.zip") as pzf:
    pzf.extractall()
```

## Upload module with twine

Upload module without error if it already exists.

`twine upload --skip-existing dist/*` 

## Get current script path

```python
import os

path=os.path.dirname(os.path.realpath(__file__))
```