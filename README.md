# Barometer

Barometer is a Python library that combines the simple thrill of logging with print
statements with the deep satisfaction of logging with a library.


```python
print(SUCCESS, "Hello")
print(INFO, "World!")
print(WARNING, "Foo")
print(ERR, "Bar")
print(DEBUG, "asdfghjkl;")
```

![output](https://i.imgur.com/IYZMtyG.png)

## Installation

Barometer has no dependencies, so you can just download the .py file and include it in your project.
Or use [pip](https://pip.pypa.io/en/stable/) to install. You know the drill.

```bash
pip install barometer
```

## Usage

```python3
from barometer import *

@barometer
def print_two_strings(s1, s2):
    print(DEBUG, f"Concatenating {s1} and {s2}})        # Add a debug level message
    try:
        result = s1 + s2
    except TypeError:
        print(ERR, "s1 and s2 must both be strings!")   # Add an error level message
    else:
        print(SUCCESS, "concatenated s1 and s2!")       # Add a success level message
        print(result)                                   # Print normally

# Default: Print non-debug log messages
print_two_strings("hello", "world")

# Print error messages and log everything to file                
print_two_string("hello", 100, log_level=DEBUG, filename="mylog.txt", verbosity=ERR)

# Just log to file
print_two_strings("hello", "world", log_level=DEBUG, filename="mylog.txt", verbosity=None)
```


## License
[MIT](https://choosealicense.com/licenses/mit/)
