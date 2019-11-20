# pyscrun
Run a Python script inside a module by its full path

Use case:

I have some scripts inside a folder, like
```
pkg
 - __init__.py
 - mod1
   - script.py
   - __init__.py
 - utils
   - stuff.py
   - ...
```

script.py has something like
```
from pkg.utils import stuff
```

If I execute it from any other directory, this will fail.

*pyscrun hacks the PYTHONPATH to find the root package path, the first one without `__init__.py`*

so 

```
pyscrun /absolute/path/to/pkg/mod1/script.py
```

Should "just work" :)
