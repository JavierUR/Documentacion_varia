# Useful python snippet

## unzip

```python
import sys
from zipfile import PyZipFile
with PyZipFile("file.zip") as pzf:
    pzf.extractall()
```

