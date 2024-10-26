# YAML Cleaner

A Python tool for cleaning and formatting YAML strings, handling common errors and inconsistencies.

## Features

- Cleans and formats YAML strings
- Handles common YAML errors and inconsistencies
- Preserves list structures
- Determines YAML types (Scalar, List, Dictionary)
- Provides detailed output for each cleaning operation

## Requirements

- Python 3.6+
- ruamel.yaml library

## Installation

1. Clone this repository:
   ```
   git clone https://github.com/yourusername/yaml-cleaner.git
   cd yaml-cleaner
   ```

2. Install the required dependencies:
   ```
   pip install ruamel.yaml
   ```

## Usage

The main functionality is provided by the `YAMLCleaner` class in `materials/yaml8.py`. Here's a basic example of how to use it:

```python
from materials.yaml8 import YAMLCleaner

cleaner = YAMLCleaner()
yaml_string = """
- item1
- item2
- item3
"""

result = cleaner.clean_yaml(yaml_string)

if result.is_valid():
    print("Cleaned YAML:")
    print(result.cleaned_yaml)
    print(f"YAML Type: {result.get_type_name()} (Type {result.yaml_type})")
else:
    print("Error:", result.error_message)
```

## Running Tests

The `main()` function in `materials/yaml8.py` includes a set of test cases. To run these tests, execute:

```
python materials/yaml8.py
```

This will run through various test cases and display the original YAML, cleaned YAML, parsed data, and YAML type for each case.

## Customization

You can customize the YAML cleaning process by adjusting the parameters when initializing the `YAMLCleaner` class:

```python
cleaner = YAMLCleaner(
    indent_mapping=2,
    indent_sequence=4,
    indent_offset=2,
    max_width=80
)
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Thanks to the ruamel.yaml library for providing robust YAML parsing capabilities.
- Inspired by common YAML formatting issues encountered in various projects.
