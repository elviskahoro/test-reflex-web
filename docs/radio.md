

  # Radio

The Radio component allows users to select a single option from a set of choices.

## Import

```python
import reflex as rx
```

## Usage

```python
rx.radio_group(
    ["Option 1", "Option 2", "Option 3"],
    default_value="Option 1",
)
```

## Props

| Prop | Type | Description | Default |
| ---- | ---- | ----------- | ------- |
| options | List[str] | The list of options to display. | None |
| value | str | The currently selected value. | None |
| default_value | str | The default selected value. | None |
| on_change | Callable | Function called when the selection changes. | None |

## Examples

### Basic Usage

```python
class RadioState(rx.State):
    selected: str = "Option 1"

def index():
    return rx.radio_group(
        ["Option 1", "Option 2", "Option 3"],
        value=RadioState.selected,
        on_change=RadioState.set_selected,
    )
```

### Custom Styling

```python
rx.radio_group(
    ["Red", "Green", "Blue"],
    default_value="Red",
    color_scheme="red",
    size="lg",
)
```

### Disabled Options

```python
rx.radio_group(
    [
        rx.radio("Enabled", value="enabled"),
        rx.radio("Disabled", value="disabled", is_disabled=True),
    ],
    default_value="enabled",
)
```

## Styling

The Radio component can be styled using Reflex's styling props:

```python
rx.radio_group(
    ["Option 1", "Option 2", "Option 3"],
    spacing="1em",
    direction="column",
    color_scheme="green",
)
```

  