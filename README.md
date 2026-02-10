# Copilot CLI Session Selector

Simple tools to list and resume GitHub Copilot CLI sessions.

## Tools

- **copilot-sessions** - List all sessions with date and first user message
- **copilot-wrapper** - Wrapper adding `-S`/`--select` option for interactive session selection

## Installation

```bash
# Install fzf (required for interactive selection)
sudo dnf install fzf  # or apt install fzf

# Copy tools
sudo cp copilot-sessions /usr/local/bin/
sudo cp copilot-wrapper /usr/local/bin/

# Set up wrapper (repeat after each copilot upgrade)
sudo mv /usr/local/bin/copilot /usr/local/bin/copilot-real
sudo ln -s /usr/local/bin/copilot-wrapper /usr/local/bin/copilot
```

## Usage

```bash
# List sessions
copilot-sessions

# Interactive session selection
copilot -S
copilot --select

# Normal copilot usage (unchanged)
copilot [any options]
```

## Output Example

```
ID        DATE                 FIRST MESSAGE
==============================================================================
80740019  2025-10-16 14:13:32  in current folder there is the mariadb 11.8...
4929eb68  2025-10-16 15:57:34  I want to create a script to patch mariadb...
```

## License

MIT
