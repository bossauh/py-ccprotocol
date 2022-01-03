# CC Protocol
A python implementation of the [CC Protocol](https://github.com/bossauh/cc-protocol) made by me.

# API Reference
## Turtle
```py
# Initializing a Turtle class
from ccprotocol import Turtle
turtle = Turtle("path/to/computer/id")
```

### Methods
A reference to the rest of the methods the Turtle class exposes can be found [here](https://tweaked.cc/module/turtle.html). 
Those lua functions basically just translates to python functions.

### `inventory_items` :
    Returns a list containing the items in the turtle's inventory in a dictionary format.

### `auto_refuel` :
    Sorts the turtle's inventory and refuels it if there's fuel. Returns the new fuel level.

### Properties

### `location` :
    Returns a tuple (x, y, z) of the current location of the turtle or None if getting the location fails. Using this requires you to have the wireless modem equipped and also a GPS system setup.

## Peripheral
Each turtle class will have its own peripheral attribute. This attribute is a reference to the peripheral class.

### Methods
For every method that requires a name parameter, you can pass in either it's position name or the actual name of the peripheral, i.e., what type is it. This however takes more time to run compared to just passing the location.


For more information about the peripheral API of computer craft, see [here](https://tweaked.cc/module/peripheral.html)

### `getNames` : 
    Returns a list of peripheral names. These names are actually `top, left, bottom, right` rather than their actual names.

### `isPresent(name: str)` :
    Returns a boolean indicating if the peripheral provided is present.

### `getType(name: str)` :
    Returns the type of the peripheral.

### `getMethods(name: str)` :
    Returns a list of methods that the peripheral has.

### `peripheral_call(name: str, method: str, *args)` :
    Calls a method on the peripheral. Check the documentation i've linked above for more information.

# Notes
- Every time you run a command, there is a 2 second timeout limit. If the "server" does not respond within 2 seconds. A `TimeoutError` is then raised. This is just a fancy way of saying server dead.
- When hitting Ctrl + C or basically performing a KeyboardInterrupt, the command you're trying to run will raise a IOError.
