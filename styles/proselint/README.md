# proselint

> [`proselint`](https://github.com/amperser/proselint/) places the world’s greatest writers and editors by your side, where they whisper suggestions on how to improve your prose.

This repository contains a [Vale-compatible](https://github.com/errata-ai/vale) implementation of the guidelines enforced by the [proselint](http://proselint.com/) linter.

## Getting Started

> **proselint requires Vale >= 1.7.0**.

Download the [latest release](https://github.com/errata-ai/proselint/releases), copy the "proselint" directory to your `StylesPath`, and include it in your configuration file:

```ini
# This goes in a file named either `.vale.ini` or `_vale.ini`.
StylesPath = path/to/some/directory
MinAlertLevel = warning # suggestion, warning or error

# Only Markdown and .txt files; change to whatever you're using.
[*.{md,txt}]
# List of styles to load.
BasedOnStyles = proselint
```

See [Usage](https://github.com/errata-ai/vale/#usage) for more information.
