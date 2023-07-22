# agentlogger <a href="https://discord.gg/qetWd7J9De"><img style="float: right" src="https://dcbadge.vercel.app/api/server/qetWd7J9De" alt=""></a>

Simple, colorful terminal logs and logfiles.

<img src="resources/image.jpg">

# Installation

```bash
pip install agentlogger
```

## Quickstart

Here is a quick overview of how you can use Agent Logger in your project:

```python
from agentlogger import log, print_header, write_to_file

# Print a styled log message to the console
log('Test message', type='info')
# ╭─ (info) agentlogger ─╮
# │ Test message         │
# ╰──────────────────────╯

# Display a big styled header in the console
print_header('Test header', font='slant', color='blue')
#    ______          __     __                   __
#  /_  __/__  _____/ /_   / /_  ___  ____ _____/ /__  _____
#   / / / _ \/ ___/ __/  / __ \/ _ \/ __ `/ __  / _ \/ ___/
#  / / /  __(__  ) /_   / / / /  __/ /_/ / /_/ /  __/ /
# /_/  \___/____/\__/  /_/ /_/\___/\__,_/\__,_/\___/_/


# Write a log message to a file
write_to_file('More log content', source='tests.py', type='test_write_to_file')
# ========================  tests.py: test_write_to_file  ========================

# More log content

# ================================================================================

```

## Documentation

Here is an overview of the available functions:

### `log(content, source=None, title="agentlogger", type="info", color="blue", type_colors=DEFAULT_TYPE_COLORS, expand=True, panel=True, log=True)`

This function is used to create an event with provided metadata and saves it to the event log file.

#### Colors

The available log color options are: black, red, green, yellow, blue, magenta, cyan and white. The color of your log will be determined by the type of the log, if the type log is in the dictionary. If the type is not in the log, it will look at the "color" argument. You can also provide your own type dictionary.

#### Arguments:

- `content`: Content of the event.
- `source`: Source of the event, e.g. a function name. Defaults to None.
- `title`: Title of the event. Defaults to "agentlogger".
- `type`: Type of the event. Defaults to "info".
- `type_colors`: Dictionary with event types as keys and colors as values. Defaults to a predefined dictionary.
- `expand`: Determines if the output should be within a Panel. Defaults to True.
- `panel`: Determines if the output should be displayed inside a bordered box panel. Defaults to True.
- `log`: Determines if the output should be logged. Defaults to True.

### `print_header(text="agentlogger", font="slant", color="yellow", width=console.width, justify="left")`

This function displays a header with the provided text and color.

#### Header Fonts

The header fonts come from the FIGlet library. You can find a list of available fonts [here](http://www.figlet.org/fontdb.cgi).

#### Colors

The color options are the same as the ones used in the `log` function: black, red, green, yellow, blue, magenta, cyan and white.

#### Arguments:

- `text`: Text to be displayed in the header. Defaults to "agentlogger".
- `font`: Font to be used in the header. Defaults to "slant".
- `color`: Color to be used in the header. Defaults to "yellow".
- `width`: Width of the console. Defaults to the console width.
- `justify`: Justification of the text in the header. Defaults to "left".

### `write_to_file(content, source=None, type=None, filename="events.log", separator_width=80)`

This function writes content to the event log file.

#### Arguments:

- `content`: Content to be written in the log file.
- `source`: Source of the event, e.g. a function name. Defaults to None.
- `type`: Type of the event. Defaults to None.
- `filename`: Name of the file where the content will be written. Defaults to "events.log".
- `separator_width`: Width of the separator. Defaults to 80.

#### Default Type Colors

Some log types are mapped to colors by default. You can also create your own dictionary and pass it to the `log` function. The default dictionary is:

```
unknown: white
system: magenta
info: blue
warning: yellow
success: green
error: red
start: green
stop: red
pause: yellow
epoch: white
summary: cyan
reasoning: cyan
action: green
prompt: cyan
```

## Examples

Here are a few examples of how you can use this library:

```python
# Log an info message to the console
log('Application started', type='info')

# Log a warning message to the console
log('Low on disk space', type='warning')

# Log an error message to the console without a panel
log('Failed to connect to the database', type='error', panel=False)

# Display a big styled header
print_header('Welcome to My Application')

# Write a log message to a file
write_to_file('User logged in', source='auth.py', type='info')
```

## Tests

You can run tests using pytest:

```bash
pytest test.py
```

# Contributions Welcome

If you like this library and want to contribute in any way, please feel free to submit a PR and it will be reviewed. The goal of this project is simplicity and accessibility using plain language and sane defaults, so please keep that in mind when submitting a PR.

<img src="resources/youcreatethefuture.jpg">
