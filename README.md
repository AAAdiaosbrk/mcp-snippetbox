# mcp-snippetbox

A small MCP server exposing my notes to Claude Desktop

## How to use

```bash
# claude_desktop_config.json  (use ABSOLUTE paths: Claude does not
# run from the repo directory, so a bare "server.py" is not found)
# {
#   "mcpServers": {
#     "notes-box": {
#       "command": "python",
#       "args": ["/abs/path/to/mcp-snippetbox/server.py"],
#       "env": {"MCP_NOTES_FILE": "/abs/path/to/notes.json"}
#     }
#   }
# }
python server.py --help
```

## Install

```bash
pip install -r requirements.txt
```

## Highlights

- Includes a Claude Desktop config snippet with absolute paths
- Atomic saves (temp file + os.replace) behind a write lock
- A missing note raises instead of returning the string 'not found'
- Five tools: add / get / update / delete / list notes
- Every tool carries a real docstring, so clients get descriptions
- Notes path set by MCP_NOTES_FILE or --notes-file

## Project structure

```text
├── .github/
│   └── workflows/
│       └── ci.yml
├── docs/
│   ├── configuration.md
│   ├── development.md
│   └── usage.md
├── tests/
│   └── test_notes.py
├── .gitignore
├── CHANGELOG.md
├── CONTRIBUTING.md
├── LICENSE
├── SECURITY.md
├── requirements.txt
└── server.py
```

## Development

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
python -m pytest -q
```

## Notes

- mostly stable, edge cases remain

## License

MIT. Do whatever you want.
