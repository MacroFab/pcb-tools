pcb-tools - unofficial but maintained fork
============
[![CI](https://github.com/MacroFab/pcb-tools/workflows/pcb-tools/badge.svg)](https://github.com/MacroFab/pcb-tools/actions)
[![Coverage](https://codecov.io/gh/MacroFab/pcb-tools/branch/master/graph/badge.svg)](https://codecov.io/gh/MacroFab/pcb-tools)
[![Docs](https://readthedocs.org/projects/pcb-tools/badge/?version=latest)](https://readthedocs.org/projects/pcb-tools/?badge=latest)

Tools to handle Gerber and Excellon files in Python.
In the pipeline column output the status of a certain step in github actions workflow
| Version | Supported          | Notes |
| ------- | ------------------ | -------- |
| 3.9.x   | [![Python 3.9](https://github.com/MacroFab/pcb-tools/actions/workflows/python39.yaml/badge.svg)](https://github.com/MacroFab/pcb-tools/actions/workflows/python39.yaml) | |
| 3.10.x  | [![Python 3.10](https://github.com/MacroFab/pcb-tools/actions/workflows/python310.yaml/badge.svg)](https://github.com/MacroFab/pcb-tools/actions/workflows/python310.yaml) | |
| 3.11.x  | [![Python 3.11](https://github.com/MacroFab/pcb-tools/actions/workflows/python311.yaml/badge.svg)](https://github.com/MacroFab/pcb-tools/actions/workflows/python311.yaml) | |
| 3.12.x  | [![Python 3.12](https://github.com/MacroFab/pcb-tools/actions/workflows/python312.yaml/badge.svg)](https://github.com/MacroFab/pcb-tools/actions/workflows/python312.yaml) | |
| 3.13.x  | [![Python 3.13](https://github.com/MacroFab/pcb-tools/actions/workflows/python313.yaml/badge.svg)](https://github.com/MacroFab/pcb-tools/actions/workflows/python313.yaml) | |

Usage Example:
---------------

```py
import gerber
from gerber.render import GerberCairoContext

# Read gerber and Excellon files
top_copper = gerber.read('example.GTL')
nc_drill = gerber.read('example.txt')

# Rendering context
ctx = GerberCairoContext()

# Create SVG image
top_copper.render(ctx)
nc_drill.render(ctx, 'composite.svg')
```

Rendering Examples:
-------------------
### Top Composite rendering
![Composite Top Image](examples/cairo_example.png)
![Composite Bottom Image](examples/cairo_bottom.png)

Source code for this example can be found [here](examples/cairo_example.py).


Install from source:
```
$ git clone https://github.com/MacroFab/pcb-tools.git
$ cd pcb-tools
$ pip install -r requirements.txt
$ python setup.py install
```

Documentation:
--------------
[PCB Tools Documentation](http://pcb-tools.readthedocs.org/en/latest/)


Development and Testing:
------------------------

Dependencies for developing and testing pcb-tools are listed in requirements-dev.txt. Use of a virtual environment is strongly recommended.

    $ virtualenv venv
    $ source venv/bin/activate
    (venv)$ pip install -r requirements-dev.txt
    (venv)$ pip install -e .

We use [pytest](https://docs.pytest.org/en/latest/) to run pcb-tools's suite of unittests and doctests.

    (venv)$ pytest
