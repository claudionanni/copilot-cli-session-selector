# Copilot CLI Session Selector

Simple tools to list and resume GitHub Copilot CLI sessions.

## Tools

- **copilot-sessions** - List all sessions with date, directory and first user message
- **copilot-wrapper** - Wrapper adding session selection and search to the `copilot` command

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
# List all sessions
copilot -L

# List sessions filtered by keyword
copilot -L -k galera

# Interactive session selection (fzf)
copilot -S

# Search by keyword and select (fzf)
copilot -K mariadb

# Normal copilot usage (unchanged)
copilot [any options]
```

### Standalone (without wrapper)

```bash
copilot-sessions              # list all
copilot-sessions -k galera    # filter by keyword
copilot-sessions -s           # interactive select (returns ID)
```

## Output Example

```
ID        DATE                 DIRECTORY                       FIRST MESSAGE
====================================================================================================================
80740019  2025-10-16 14:13:32                                  in current folder there is the mariadb 11.8 source...
781c066f  2026-02-20 14:49:03  github/epoch-audio-mastering-t  I want to make a virtual artist to publish music...
140a46bc  2026-02-21 21:43:08  github/epoch-audio-mastering-t  we left a session yesterday about a master pipeline...
```

## License

MIT
