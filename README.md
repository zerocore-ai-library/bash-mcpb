# Bash MCP Server

Shell command execution for AI agents. Based on [Claude Code's Bash tool design](https://gist.github.com/bgauryy/0cdb9aa337d01ae5bd0c803943aa36bd).

## Setup

### Using tool CLI

Install the CLI from https://github.com/zerocore-ai/tool-cli

```bash
# Install from tool.store
tool install library/bash
```

```bash
# View available tools
tool info library/bash
```

```bash
# Execute a command
tool call library/bash -m exec -p command="echo hello"
```

```bash
# Run a command with timeout
tool call library/bash -m exec -p command="sleep 5" -p timeout_ms=10000
```

## Tools

### `exec`

Execute a shell command and return its output.

**Input:**
| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `command` | string | Yes | The shell command to execute |
| `description` | string | No | Short description (5-10 words) of what the command does |
| `timeout_ms` | integer | No | Timeout in milliseconds (default: 120000, max: 600000) |
| `working_directory` | string | No | Working directory for command execution |

**Output:**
| Field | Type | Description |
|-------|------|-------------|
| `stdout` | string | Standard output from the command |
| `stderr` | string | Standard error from the command |
| `exit_code` | integer | Exit code of the command (0 = success) |
| `stdout_truncated` | boolean | Whether stdout was truncated due to size limits |
| `stderr_truncated` | boolean | Whether stderr was truncated due to size limits |
| `duration_ms` | integer | Actual execution duration in milliseconds |

## License

Apache-2.0
