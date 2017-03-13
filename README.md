# latex2svg

Python wrapper and CLI utility to render LaTeX markup and equations as SVG using
[dvisvgm](http://dvisvgm.bplaced.net/).


## Usage

### Python 3 module

```python
from latex2svg import latex2svg
out = latex2svg(r'\( e^{i \pi} + 1 = 0 \)')
print(out['depth'])  # baseline position in em
print(out['svg'])  # rendered SVG
```

### CLI utility

    $ ./latex2svg.py --help
    usage: latex2svg.py [-h] [--preamble PREAMBLE]
    
    Render LaTeX code from stdin as SVG to stdout. Writes metadata (baseline
    position, width, height in em units) as JSON to stderr.
    
    optional arguments:
      -h, --help           show this help message and exit
      --preamble PREAMBLE  LaTeX preamble code to read from file
    
    $ echo "\\( e^{i \\pi} + 1 = 0 \\)" | ./latex2svg.py > euler-identity.svg
    {"width": 4.458858333333334, "height": 0.8262691666666666, "depth": 0.012687666666666667}

Resulting SVG:
<img src="https://cdn.rawgit.com/tuxu/latex2svg/0.1.0/euler-identity.svg" style="height: 0.826em; vertical-align: -0.013em;" alt="Euler's identity" />

## License

This project is licensed under the MIT license. See [LICENSE.md](LICENSE.md) for
details.

© 2017 [Tino Wagner](http://www.tinowagner.com/)
