# OpenCode Documentation

## Table of Contents
- [Opencode AI](#opencode-ai)
- [Opencode AI Config JSON](#opencode-ai-config-json)
- [Opencode AI Docs](#opencode-ai-docs)
- [Opencode AI Docs CLI](#opencode-ai-docs-cli)
- [Opencode AI Docs Config](#opencode-ai-docs-config)
- [Opencode AI Docs Enterprise](#opencode-ai-docs-enterprise)
- [Opencode AI Docs Keybinds](#opencode-ai-docs-keybinds)
- [Opencode AI Docs MCP Servers](#opencode-ai-docs-mcp-servers)
- [Opencode AI Docs Models](#opencode-ai-docs-models)
- [Opencode AI Docs Modes](#opencode-ai-docs-modes)
- [Opencode AI Docs Rules](#opencode-ai-docs-rules)
- [Opencode AI Docs Share](#opencode-ai-docs-share)
- [Opencode AI Docs Themes](#opencode-ai-docs-themes)
- [Opencode AI Docs Troubleshooting](#opencode-ai-docs-troubleshooting)

---

## Opencode AI

[Skip to content](https://opencode.ai/#_top)

[Docs](https://opencode.ai/docs)

` curl -fsSL https://opencode.ai/install | bash `

[GitHub](https://github.com/sst/opencode)

- **Native TUI**: A responsive, native, themeable terminal UI.
- **LSP enabled**: Automatically loads the right LSPs for the LLM.
- **Multi-session**: Start multiple agents in parallel on the same project.
- **Shareable links**: Share a link to any sessions for reference or to debug.
- **Claude Pro**: Log in with Anthropic to use your Claude Pro or Max account.
- **Use any model**: Supports 75+ LLM providers through [Models.dev](https://models.dev/), including local models.

opencode TUI with the tokyonight theme

![opencode TUI with the tokyonight theme](https://opencode.ai/_astro/screenshot-splash.Br7Db4P4_ZUNKo1.webp)

---

## Opencode AI Config JSON

```json
{
  "type": "object",
  "properties": {
    "$schema": {
      "type": "string",
      "description": "JSON schema reference for configuration validation"
    },
    "theme": {
      "type": "string",
      "description": "Theme name to use for the interface"
    },
    "keybinds": {
      "type": "object",
      "properties": {
        "leader": {
          "type": "string",
          "default": "ctrl+x",
          "description": "Leader key for keybind combinations\n\ndefault: `ctrl+x`",
          "examples": [
            "ctrl+x"
          ]
        },
        "app_help": {
          "type": "string",
          "default": "<leader>h",
          "description": "Show help dialog\n\ndefault: `<leader>h`",
          "examples": [
            "<leader>h"
          ]
        },
        "switch_mode": {
          "type": "string",
          "default": "tab",
          "description": "Switch mode\n\ndefault: `tab`",
          "examples": [
            "tab"
          ]
        },
        "editor_open": {
          "type": "string",
          "default": "<leader>e",
          "description": "Open external editor\n\ndefault: `<leader>e`",
          "examples": [
            "<leader>e"
          ]
        },
        "session_new": {
          "type": "string",
          "default": "<leader>n",
          "description": "Create a new session\n\ndefault: `<leader>n`",
          "examples": [
            "<leader>n"
          ]
        },
        "session_list": {
          "type": "string",
          "default": "<leader>l",
          "description": "List all sessions\n\ndefault: `<leader>l`",
          "examples": [
            "<leader>l"
          ]
        },
        "session_share": {
          "type": "string",
          "default": "<leader>s",
          "description": "Share current session\n\ndefault: `<leader>s`",
          "examples": [
            "<leader>s"
          ]
        },
        "session_unshare": {
          "type": "string",
          "default": "<leader>u",
          "description": "Unshare current session\n\ndefault: `<leader>u`",
          "examples": [
            "<leader>u"
          ]
        },
        "session_interrupt": {
          "type": "string",
          "default": "esc",
          "description": "Interrupt current session\n\ndefault: `esc`",
          "examples": [
            "esc"
          ]
        },
        "session_compact": {
          "type": "string",
          "default": "<leader>c",
          "description": "Compact the session\n\ndefault: `<leader>c`",
          "examples": [
            "<leader>c"
          ]
        },
        "tool_details": {
          "type": "string",
          "default": "<leader>d",
          "description": "Toggle tool details\n\ndefault: `<leader>d`",
          "examples": [
            "<leader>d"
          ]
        },
        "model_list": {
          "type": "string",
          "default": "<leader>m",
          "description": "List available models\n\ndefault: `<leader>m`",
          "examples": [
            "<leader>m"
          ]
        },
        "theme_list": {
          "type": "string",
          "default": "<leader>t",
          "description": "List available themes\n\ndefault: `<leader>t`",
          "examples": [
            "<leader>t"
          ]
        },
        "file_list": {
          "type": "string",
          "default": "<leader>f",
          "description": "List files\n\ndefault: `<leader>f`",
          "examples": [
            "<leader>f"
          ]
        },
        "file_close": {
          "type": "string",
          "default": "esc",
          "description": "Close file\n\ndefault: `esc`",
          "examples": [
            "esc"
          ]
        },
        "file_search": {
          "type": "string",
          "default": "<leader>/",
          "description": "Search file\n\ndefault: `<leader>/`",
          "examples": [
            "<leader>/"
          ]
        },
        "file_diff_toggle": {
          "type": "string",
          "default": "<leader>v",
          "description": "Split/unified diff\n\ndefault: `<leader>v`",
          "examples": [
            "<leader>v"
          ]
        },
        "project_init": {
          "type": "string",
          "default": "<leader>i",
          "description": "Create/update AGENTS.md\n\ndefault: `<leader>i`",
          "examples": [
            "<leader>i"
          ]
        },
        "input_clear": {
          "type": "string",
          "default": "ctrl+c",
          "description": "Clear input field\n\ndefault: `ctrl+c`",
          "examples": [
            "ctrl+c"
          ]
        },
        "input_paste": {
          "type": "string",
          "default": "ctrl+v",
          "description": "Paste from clipboard\n\ndefault: `ctrl+v`",
          "examples": [
            "ctrl+v"
          ]
        },
        "input_submit": {
          "type": "string",
          "default": "enter",
          "description": "Submit input\n\ndefault: `enter`",
          "examples": [
            "enter"
          ]
        },
        "input_newline": {
          "type": "string",
          "default": "shift+enter,ctrl+j",
          "description": "Insert newline in input\n\ndefault: `shift+enter,ctrl+j`",
          "examples": [
            "shift+enter,ctrl+j"
          ]
        },
        "messages_page_up": {
          "type": "string",
          "default": "pgup",
          "description": "Scroll messages up by one page\n\ndefault: `pgup`",
          "examples": [
            "pgup"
          ]
        },
        "messages_page_down": {
          "type": "string",
          "default": "pgdown",
          "description": "Scroll messages down by one page\n\ndefault: `pgdown`",
          "examples": [
            "pgdown"
          ]
        },
        "messages_half_page_up": {
          "type": "string",
          "default": "ctrl+alt+u",
          "description": "Scroll messages up by half page\n\ndefault: `ctrl+alt+u`",
          "examples": [
            "ctrl+alt+u"
          ]
        },
        "messages_half_page_down": {
          "type": "string",
          "default": "ctrl+alt+d",
          "description": "Scroll messages down by half page\n\ndefault: `ctrl+alt+d`",
          "examples": [
            "ctrl+alt+d"
          ]
        },
        "messages_previous": {
          "type": "string",
          "default": "ctrl+up",
          "description": "Navigate to previous message\n\ndefault: `ctrl+up`",
          "examples": [
            "ctrl+up"
          ]
        },
        "messages_next": {
          "type": "string",
          "default": "ctrl+down",
          "description": "Navigate to next message\n\ndefault: `ctrl+down`",
          "examples": [
            "ctrl+down"
          ]
        },
        "messages_first": {
          "type": "string",
          "default": "ctrl+g",
          "description": "Navigate to first message\n\ndefault: `ctrl+g`",
          "examples": [
            "ctrl+g"
          ]
        },
        "messages_last": {
          "type": "string",
          "default": "ctrl+alt+g",
          "description": "Navigate to last message\n\ndefault: `ctrl+alt+g`",
          "examples": [
            "ctrl+alt+g"
          ]
        },
        "messages_layout_toggle": {
          "type": "string",
          "default": "<leader>p",
          "description": "Toggle layout\n\ndefault: `<leader>p`",
          "examples": [
            "<leader>p"
          ]
        },
        "messages_copy": {
          "type": "string",
          "default": "<leader>y",
          "description": "Copy message\n\ndefault: `<leader>y`",
          "examples": [
            "<leader>y"
          ]
        },
        "messages_revert": {
          "type": "string",
          "default": "<leader>r",
          "description": "Revert message\n\ndefault: `<leader>r`",
          "examples": [
            "<leader>r"
          ]
        },
        "app_exit": {
          "type": "string",
          "default": "ctrl+c,<leader>q",
          "description": "Exit the application\n\ndefault: `ctrl+c,<leader>q`",
          "examples": [
            "ctrl+c,<leader>q"
          ]
        }
      },
      "additionalProperties": false,
      "description": "Custom keybind configurations"
    },
    "share": {
      "type": "string",
      "enum": [
        "auto",
        "disabled"
      ],
      "description": "Control sharing behavior: 'auto' enables automatic sharing, 'disabled' disables all sharing"
    },
    "autoshare": {
      "type": "boolean",
      "description": "@deprecated Use 'share' field instead. Share newly created sessions automatically"
    },
    "autoupdate": {
      "type": "boolean",
      "description": "Automatically update to the latest version"
    },
    "disabled_providers": {
      "type": "array",
      "items": {
        "type": "string"
      },
      "description": "Disable providers that are loaded automatically"
    },
    "model": {
      "type": "string",
      "description": "Model to use in the format of provider/model, eg anthropic/claude-2"
    },
    "mode": {
      "type": "object",
      "properties": {
        "build": {
          "type": "object",
          "properties": {
            "model": {
              "type": "string"
            },
            "prompt": {
              "type": "string"
            },
            "tools": {
              "type": "object",
              "additionalProperties": {
                "type": "boolean"
              }
            }
          },
          "additionalProperties": false
        },
        "plan": {
          "$ref": "#/properties/mode/properties/build"
        }
      },
      "additionalProperties": {
        "$ref": "#/properties/mode/properties/build"
      }
    },
    "log_level": {
      "type": "string",
      "enum": [
        "DEBUG",
        "INFO",
        "WARN",
        "ERROR"
      ],
      "description": "Minimum log level to write to log files"
    },
    "provider": {
      "type": "object",
      "additionalProperties": {
        "type": "object",
        "properties": {
          "api": {
            "type": "string"
          },
          "name": {
            "type": "string"
          },
          "env": {
            "type": "array",
            "items": {
              "type": "string"
            }
          },
          "id": {
            "type": "string"
          },
          "npm": {
            "type": "string"
          },
          "models": {
            "type": "object",
            "additionalProperties": {
              "type": "object",
              "properties": {
                "id": {
                  "type": "string"
                },
                "name": {
                  "type": "string"
                },
                "release_date": {
                  "type": "string"
                },
                "attachment": {
                  "type": "boolean"
                },
                "reasoning": {
                  "type": "boolean"
                },
                "temperature": {
                  "type": "boolean"
                },
                "tool_call": {
                  "type": "boolean"
                },
                "cost": {
                  "type": "object",
                  "properties": {
                    "input": {
                      "type": "number"
                    },
                    "output": {
                      "type": "number"
                    },
                    "cache_read": {
                      "type": "number"
                    },
                    "cache_write": {
                      "type": "number"
                    }
                  },
                  "required": [
                    "input",
                    "output"
                  ],
                  "additionalProperties": false
                },
                "limit": {
                  "type": "object",
                  "properties": {
                    "context": {
                      "type": "number"
                    },
                    "output": {
                      "type": "number"
                    }
                  },
                  "required": [
                    "context",
                    "output"
                  ],
                  "additionalProperties": false
                },
                "options": {
                  "type": "object",
                  "additionalProperties": {}
                }
              },
              "additionalProperties": false
            }
          },
          "options": {
            "type": "object",
            "additionalProperties": {}
          }
        },
        "required": [
          "models"
        ],
        "additionalProperties": false
      },
      "description": "Custom provider configurations and model overrides"
    },
    "mcp": {
      "type": "object",
      "additionalProperties": {
        "anyOf": [
          {
            "type": "object",
            "properties": {
              "type": {
                "type": "string",
                "const": "local",
                "description": "Type of MCP server connection"
              },
              "command": {
                "type": "array",
                "items": {
                  "type": "string"
                },
                "description": "Command and arguments to run the MCP server"
              },
              "environment": {
                "type": "object",
                "additionalProperties": {
                  "type": "string"
                },
                "description": "Environment variables to set when running the MCP server"
              },
              "enabled": {
                "type": "boolean",
                "description": "Enable or disable the MCP server on startup"
              }
            },
            "required": [
              "type",
              "command"
            ],
            "additionalProperties": false
          },
          {
            "type": "object",
            "properties": {
              "type": {
                "type": "string",
                "const": "remote",
                "description": "Type of MCP server connection"
              },
              "url": {
                "type": "string",
                "description": "URL of the remote MCP server"
              },
              "enabled": {
                "type": "boolean",
                "description": "Enable or disable the MCP server on startup"
              }
            },
            "required": [
              "type",
              "url"
            ],
            "additionalProperties": false
          }
        ]
      },
      "description": "MCP (Model Context Protocol) server configurations"
    },
    "instructions": {
      "type": "array",
      "items": {
        "type": "string"
      },
      "description": "Additional instruction files or patterns to include"
    },
    "experimental": {
      "type": "object",
      "properties": {
        "hook": {
          "type": "object",
          "properties": {
            "file_edited": {
              "type": "object",
              "additionalProperties": {
                "type": "array",
                "items": {
                  "type": "object",
                  "properties": {
                    "command": {
                      "type": "array",
                      "items": {
                        "type": "string"
                      }
                    },
                    "environment": {
                      "type": "object",
                      "additionalProperties": {
                        "type": "string"
                      }
                    }
                  },
                  "required": [
                    "command"
                  ],
                  "additionalProperties": false
                }
              }
            },
            "session_completed": {
              "type": "array",
              "items": {
                "type": "object",
                "properties": {
                  "command": {
                    "type": "array",
                    "items": {
                      "type": "string"
                    }
                  },
                  "environment": {
                    "type": "object",
                    "additionalProperties": {
                      "type": "string"
                    }
                  }
                },
                "required": [
                  "command"
                ],
                "additionalProperties": false
              }
            }
          },
          "additionalProperties": false
        }
      },
      "additionalProperties": false
    }
  },
  "additionalProperties": false,
  "$schema": "http://json-schema.org/draft-07/schema#"
}

```

---

## Opencode AI Docs

[Skip to content](https://opencode.ai/docs/#_top)

# Intro

Get started with opencode.

[**opencode**](https://opencode.ai/) is an AI coding agent built for the terminal. It features:

- A responsive, native, themeable terminal UI.
- Automatically loads the right LSPs, so the LLMs make fewer mistakes.
- Have multiple agents working in parallel on the same project.
- Create shareable links to any session for reference or to debug.
- Log in with Anthropic to use your Claude Pro or Claude Max account.
- Supports 75+ LLM providers through [Models.dev](https://models.dev/), including local models.

![opencode TUI with the opencode theme](https://opencode.ai/_astro/screenshot.B4yUNM4n_dwGlE.webp)

* * *

## [Install](https://opencode.ai/docs/#install)

- [npm](https://opencode.ai/docs/#tab-panel-0)
- [Bun](https://opencode.ai/docs/#tab-panel-1)
- [pnpm](https://opencode.ai/docs/#tab-panel-2)
- [Yarn](https://opencode.ai/docs/#tab-panel-3)

```

npm install -g opencode-ai
```

You can also install the opencode binary through the following.

##### [Using the install script](https://opencode.ai/docs/#using-the-install-script)

```

curl -fsSL https://opencode.ai/install | bash
```

##### [Using Homebrew on macOS](https://opencode.ai/docs/#using-homebrew-on-macos)

```

brew install sst/tap/opencode
```

##### [Using Paru on Arch Linux](https://opencode.ai/docs/#using-paru-on-arch-linux)

```

paru -S opencode-bin
```

##### [Windows](https://opencode.ai/docs/#windows)

Right now the automatic installation methods do not work properly on Windows. However you can grab the binary from the [Releases](https://github.com/sst/opencode/releases).

* * *

## [Providers](https://opencode.ai/docs/#providers)

We recommend signing up for Claude Pro or Max, running `opencode auth login` and selecting Anthropic. It’s the most cost-effective way to use opencode.

```

$ opencode auth login

┌  Add credential

│

◆  Select provider

│  ● Anthropic (recommended)

│  ○ OpenAI

│  ○ Google

│  ○ Amazon Bedrock

│  ○ Azure

│  ○ DeepSeek

│  ○ Groq

│  ...

└
```

opencode is powered by the provider list at [Models.dev](https://models.dev/), so you can use `opencode auth login` to configure API keys for any provider you’d like to use. This is stored in `~/.local/share/opencode/auth.json`.

The Models.dev dataset is also used to detect common environment variables like `OPENAI_API_KEY` to autoload that provider.

If there are additional providers you want to use you can submit a PR to the [Models.dev repo](https://github.com/sst/models.dev). You can also [add them to your config](https://opencode.ai/docs/config) for yourself.

---

## Opencode AI Docs CLI

[Skip to content](https://opencode.ai/docs/cli/#_top)

# CLI

The opencode CLI options and commands.

Running the opencode CLI starts it for the current directory.

```

opencode
```

Or you can start it for a specific working directory.

```

opencode /path/to/project
```

* * *

## [Commands](https://opencode.ai/docs/cli/#commands)

The opencode CLI also has the following commands.

* * *

### [run](https://opencode.ai/docs/cli/#run)

Run opencode in non-interactive mode by passing a prompt directly.

```

opencode run [message..]
```

This is useful for scripting, automation, or when you want a quick answer without launching the full TUI. For example.

```

opencode run Explain the use of context in Go
```

#### [Flags](https://opencode.ai/docs/cli/#flags)

| Flag | Short | Description |
| --- | --- | --- |
| `--continue` | `-c` | Continue the last session |
| `--session` | `-s` | Session ID to continue |
| `--share` |  | Share the session |
| `--model` | `-m` | Model to use in the form of provider/model |

* * *

### [auth](https://opencode.ai/docs/cli/#auth)

Command to manage credentials and login for providers.

```

opencode auth [command]
```

* * *

#### [login](https://opencode.ai/docs/cli/#login)

Logs you into a provider and saves them in the credentials file in `~/.local/share/opencode/auth.json`.

```

opencode auth login
```

When opencode starts up it will loads the providers from the credentials file. And if there are any keys defined in your environments or a `.env` file in your project.

* * *

#### [list](https://opencode.ai/docs/cli/#list)

Lists all the authenticated providers as stored in the credentials file.

```

opencode auth list
```

Or the short version.

```

opencode auth ls
```

* * *

#### [logout](https://opencode.ai/docs/cli/#logout)

Logs you out of a provider by clearing it from the credentials file.

```

opencode auth logout
```

* * *

### [upgrade](https://opencode.ai/docs/cli/#upgrade)

Updates opencode to the latest version or a specific version.

```

opencode upgrade [target]
```

To upgrade to the latest version.

```

opencode upgrade
```

To upgrade to a specific version.

```

opencode upgrade v0.1.48
```

* * *

## [Flags](https://opencode.ai/docs/cli/#flags-1)

The opencode CLI takes the following flags.

| Flag | Short | Description |
| --- | --- | --- |
| `--help` | `-h` | Display help |
| `--version` |  | Print version number |
| `--print-logs` |  | Print logs to stderr |
| `--prompt` | `-p` | Prompt to use |
| `--model` | `-m` | Model to use in the form of provider/model |
| `--mode` |  | Mode to use |

---

## Opencode AI Docs Config

[Skip to content](https://opencode.ai/docs/config/#_top)

# Config

Using the opencode JSON config.

You can configure opencode using a JSON config file.

```

{

  "$schema": "https://opencode.ai/config.json",

  "theme": "opencode",

  "model": "anthropic/claude-sonnet-4-20250514",

  "autoshare": false,

  "autoupdate": true

}
```

This can be used to configure opencode globally or for a specific project.

* * *

### [Global](https://opencode.ai/docs/config/#global)

Place your global opencode config in `~/.config/opencode/opencode.json`. You’ll want to use the global config for things like themes, providers, or keybinds.

* * *

### [Per project](https://opencode.ai/docs/config/#per-project)

You can also add a `opencode.json` in your project. This is useful for configuring providers or modes specific to your project.

When opencode starts up, it looks for a config file in the current directory or traverse up to the nearest Git directory.

This is also safe to be checked into Git and uses the same schema as the global one.

* * *

## [Schema](https://opencode.ai/docs/config/#schema)

The config file has a schema that’s defined in [**`opencode.ai/config.json`**](https://opencode.ai/config.json).

Your editor should be able to validate and autocomplete based on the schema.

* * *

### [Modes](https://opencode.ai/docs/config/#modes)

opencode comes with two built-in modes: _build_, the default with all tools enabled. And _plan_, restricted mode with file modification tools disabled. You can override these built-in modes or define your own custom modes with the `mode` option.

```

{

  "$schema": "https://opencode.ai/config.json",

  "mode": {

    "build": { },

    "plan": { },

    "my-custom-mode": { }

  }

}
```

[Learn more here](https://opencode.ai/docs/modes).

* * *

### [Models](https://opencode.ai/docs/config/#models)

You can configure the providers and models you want to use in your opencode config through the `provider` and `model` options.

```

{

  "$schema": "https://opencode.ai/config.json",

  "provider": {},

  "model": ""

}
```

You can also configure [local models](https://opencode.ai/docs/models#local). [Learn more](https://opencode.ai/docs/models).

* * *

### [Themes](https://opencode.ai/docs/config/#themes)

You can configure the theme you want to use in your opencode config through the `theme` option.

```

{

  "$schema": "https://opencode.ai/config.json",

  "theme": ""

}
```

[Learn more here](https://opencode.ai/docs/themes).

* * *

### [Logging](https://opencode.ai/docs/config/#logging)

Logs are written to:

- **macOS/Linux**: `~/.local/share/opencode/log/`
- **Windows**: `%APPDATA%\opencode\log\`

You can configure the minimum log level through the `log_level` option.

```

{

  "$schema": "https://opencode.ai/config.json",

  "log_level": "INFO"

}
```

With the following options:

| Level | Description |
| --- | --- |
| `DEBUG` | All messages including debug information |
| `INFO` | Informational messages and above |
| `WARN` | Warnings and errors only |
| `ERROR` | Errors only |

The **default** log level is `INFO`. If you are running opencode locally in
development mode it’s set to `DEBUG`.

* * *

### [Keybinds](https://opencode.ai/docs/config/#keybinds)

You can customize your keybinds through the `keybinds` option.

```

{

  "$schema": "https://opencode.ai/config.json",

  "keybinds": {}

}
```

[Learn more here](https://opencode.ai/docs/keybinds).

* * *

### [MCP servers](https://opencode.ai/docs/config/#mcp-servers)

You can configure MCP servers you want to use through the `mcp` option.

```

{

  "$schema": "https://opencode.ai/config.json",

  "mcp": {}

}
```

[Learn more here](https://opencode.ai/docs/mcp-servers).

* * *

### [Disabled providers](https://opencode.ai/docs/config/#disabled-providers)

You can disable providers that are loaded automatically through the `disabled_providers` option. This is useful when you want to prevent certain providers from being loaded even if their credentials are available.

```

{

  "$schema": "https://opencode.ai/config.json",

  "disabled_providers": ["openai", "gemini"]

}
```

The `disabled_providers` option accepts an array of provider IDs. When a provider is disabled:

- It won’t be loaded even if environment variables are set
- It won’t be loaded even if API keys are configured through `opencode auth login`
- The provider’s models won’t appear in the model selection list

* * *

## [Variables](https://opencode.ai/docs/config/#variables)

You can use variable substitution in your config files to reference environment variables and file contents.

* * *

### [Env vars](https://opencode.ai/docs/config/#env-vars)

Use `{env:VARIABLE_NAME}` to substitute environment variables:

```

{

  "$schema": "https://opencode.ai/config.json",

  "model": "{env:OPENCODE_MODEL}",

  "provider": {

    "anthropic": {

      "api_key": "{env:ANTHROPIC_API_KEY}"

    }

  }

}
```

If the environment variable is not set, it will be replaced with an empty string.

* * *

### [Files](https://opencode.ai/docs/config/#files)

Use `{file:path/to/file}` to substitute the contents of a file:

```

{

  "$schema": "https://opencode.ai/config.json",

  "instructions": ["{file:./custom-instructions.md}"],

  "provider": {

    "openai": {

      "api_key": "{file:~/.secrets/openai-key}"

    }

  }

}
```

File paths can be:

- Relative to the config file directory
- Or absolute paths starting with `/` or `~`

These are useful for:

- Keeping sensitive data like API keys in separate files.
- Including large instruction files without cluttering your config.
- Sharing common configuration snippets across multiple config files.

---

## Opencode AI Docs Enterprise

[Skip to content](https://opencode.ai/docs/enterprise/#_top)

# Enterprise

Using opencode in your organization.

opencode does not store any of your code or context data. This makes it easy for
you to use opencode at your organization.

To get started, we recommend:

1. Do a trial internally with your team.
2. [**Contact us**](mailto:hello@sst.dev) to discuss pricing and implementation options.

* * *

## [Trial](https://opencode.ai/docs/enterprise/#trial)

Since opencode is open source and does not store any of your code or context data, your developers can simply [get started](https://opencode.ai/docs/) and carry out a trial.

* * *

### [Data handling](https://opencode.ai/docs/enterprise/#data-handling)

**opencode does not store your code or context data.** All processing happens locally or through direct API calls to your AI provider.

The only caveat here is the optional `/share` feature that must be manually enabled.

* * *

#### [Sharing conversations](https://opencode.ai/docs/enterprise/#sharing-conversations)

If a user enables the `/share` feature, the conversation and the data associated with it are sent to the service we use to host these shares pages at opencode.ai.

The data is currently served through our CDN’s edge network, and is cached on the edge near your users.

* * *

### [Code ownership](https://opencode.ai/docs/enterprise/#code-ownership)

**You own all code produced by opencode.** There are no licensing restrictions or ownership claims.

* * *

## [Deployment](https://opencode.ai/docs/enterprise/#deployment)

Once you have completed your trial and you are ready to self-host opencode at
your organization, you can [**contact us**](mailto:hello@sst.dev) to discuss
pricing and implementation options.

* * *

### [SSO](https://opencode.ai/docs/enterprise/#sso)

SSO integration can be implemented for enterprise deployments after your trial. Currently users manage and configure individual API keys locally.

This can be switched to a centralized authentication system that your organization uses.

* * *

### [Self-hosting](https://opencode.ai/docs/enterprise/#self-hosting)

The share feature can be self-hosted and the share pages can be made accessible
only after the user has been authenticated.

---

## Opencode AI Docs Keybinds

[Skip to content](https://opencode.ai/docs/keybinds/#_top)

# Keybinds

Customize your keybinds.

opencode has a list of keybinds that you can customize through the opencode config.

```

{

  "$schema": "https://opencode.ai/config.json",

  "keybinds": {

    "leader": "ctrl+x",

    "help": "<leader>h",

    "editor_open": "<leader>e",

    "session_new": "<leader>n",

    "session_list": "<leader>l",

    "session_share": "<leader>s",

    "session_interrupt": "esc",

    "session_compact": "<leader>c",

    "tool_details": "<leader>d",

    "model_list": "<leader>m",

    "theme_list": "<leader>t",

    "project_init": "<leader>i",

    "input_clear": "ctrl+c",

    "input_paste": "ctrl+v",

    "input_submit": "enter",

    "input_newline": "shift+enter,ctrl+j",

    "history_previous": "up",

    "history_next": "down",

    "messages_page_up": "pgup",

    "messages_page_down": "pgdown",

    "messages_half_page_up": "ctrl+alt+u",

    "messages_half_page_down": "ctrl+alt+d",

    "messages_previous": "ctrl+alt+k",

    "messages_next": "ctrl+alt+j",

    "messages_first": "ctrl+g",

    "messages_last": "ctrl+alt+g",

    "app_exit": "ctrl+c,<leader>q"

  }

}
```

## [Leader key](https://opencode.ai/docs/keybinds/#leader-key)

opencode uses a `leader` key for most keybinds. This avoids conflicts in your terminal.

By default, `ctrl+x` is the leader key and most actions require you to first press the leader key and then the shortcut. For example, to start a new session you first press `ctrl+x` and then press `n`.

You don’t need to use a leader key for your keybinds but we recommend doing so.

---

## Opencode AI Docs MCP Servers

[Skip to content](https://opencode.ai/docs/mcp-servers/#_top)

# MCP servers

Add local and remote MCP tools.

You can add external tools to opencode using the _Model Context Protocol_, or MCP. opencode supports both:

- Local servers
- And remote servers

Once added, MCP tools are automatically available to the LLM alongside built-in tools.

* * *

## [Configure](https://opencode.ai/docs/mcp-servers/#configure)

You can define MCP servers in your opencode config under `mcp`.

### [Local](https://opencode.ai/docs/mcp-servers/#local)

Add a local MCP servers under `mcp.localmcp`.

```

{

  "$schema": "https://opencode.ai/config.json",

  "mcp": {

    "localmcp": {

      "type": "local",

      "command": ["bun", "x", "my-mcp-command"],

      "enabled": true,

      "environment": {

        "MY_ENV_VAR": "my_env_var_value"

      }

    }

  }

}
```

You can also disable a server by setting `enabled` to `false`. This is useful if you want to temporarily disable a server without removing it from your config.

### [Remote](https://opencode.ai/docs/mcp-servers/#remote)

Add a remote MCP servers under `mcp.remotemcp`.

```

{

  "$schema": "https://opencode.ai/config.json",

  "mcp": {

    "remotemcp": {

      "type": "remote",

      "url": "https://my-mcp-server.com",

      "enabled": true

    }

  }

}
```

---

## Opencode AI Docs Models

[Skip to content](https://opencode.ai/docs/models/#_top)

# Models

Configuring an LLM provider and model.

opencode uses the [AI SDK](https://ai-sdk.dev/) and [Models.dev](https://models.dev/) to support for **75+ LLM providers** and it supports running local models.

* * *

## [Providers](https://opencode.ai/docs/models/#providers)

You can configure providers in your opencode config under the `provider` section.

* * *

### [Defaults](https://opencode.ai/docs/models/#defaults)

Most popular providers are preloaded by default. If you’ve added the credentials for a provider through `opencode auth login`, they’ll be available when you start opencode.

* * *

### [Custom](https://opencode.ai/docs/models/#custom)

You can add custom providers by specifying the npm package for the provider and the models you want to use.

```

{

  "$schema": "https://opencode.ai/config.json",

  "provider": {

    "openrouter": {

      "name": "OpenRouter",

      "models": {

        "weirdo/some-weird-model": {

          "name": "Claude 3.5 Sonnet"

        }

      }

    }

  }

}
```

* * *

### [Local](https://opencode.ai/docs/models/#local)

You can configure local model like ones served through LM Studio or Ollama. To
do so, you’ll need to specify a couple of things.

Here’s an example of configuring a local model from LM Studio:

```

{

  "$schema": "https://opencode.ai/config.json",

  "provider": {

    "lmstudio": {

      "npm": "@ai-sdk/openai-compatible",

      "name": "LM Studio (local)",

      "options": {

        "baseURL": "http://127.0.0.1:1234/v1"

      },

      "models": {

        "google/gemma-3n-e4b": {

          "name": "Gemma 3n-e4b (local)"

        }

      }

    }

  }

}
```

In this example:

- `lmstudio` is the custom provider ID. We’ll use this later.
- `npm` specifies the package to use for this provider. Here, `@ai-sdk/openai-compatible` is used for any OpenAI-compatible API.
- `name` is the display name for the provider in the UI.
- `options.baseURL` is the endpoint for the local server.
- `models` is a map of model IDs to their configurations. The model name will be displayed in the model selection list.

Similarly, to configure a local model from Ollama:

```

{

  "$schema": "https://opencode.ai/config.json",

  "provider": {

    "ollama": {

      "npm": "@ai-sdk/openai-compatible",

      "options": {

        "baseURL": "http://localhost:11434/v1"

      },

      "models": {

        "llama2": {}

      }

    }

  }

}
```

To set one of these as the default model, you can set the `model` key at the
root.

```

{

  "$schema": "https://opencode.ai/config.json",

  "model": "lmstudio/google/gemma-3n-e4b"

}
```

Here the full ID is `provider_id/model_id`, where `provider_id` is the key in the `provider` list we set above and `model_id` is the key from the `provider.models` list.

* * *

## [Select a model](https://opencode.ai/docs/models/#select-a-model)

If you have multiple models, you can select the model you want by typing in:

```

/models
```

* * *

## [Loading models](https://opencode.ai/docs/models/#loading-models)

When opencode starts up, it checks for the following:

1. The model list in the opencode config.



```


{

     "$schema": "https://opencode.ai/config.json",

     "model": "anthropic/claude-sonnet-4-20250514"

}
```









The format here is `provider/model`.

2. The last used model.

3. The first model using an internal priority.

---

## Opencode AI Docs Modes

[Skip to content](https://opencode.ai/docs/modes/#_top)

# Modes

Different modes for different use cases.

Modes in opencode allow you to customize the behavior, tools, and prompts for different use cases.

It comes with two built-in modes: **build** and **plan**. You can customize
these or configure your own through the opencode config.

You can switch between modes during a session or configure them in your config file.

* * *

## [Built-in](https://opencode.ai/docs/modes/#built-in)

opencode comes with two built-in modes.

* * *

### [Build](https://opencode.ai/docs/modes/#build)

Build is the **default** mode with all tools enabled. This is the standard mode for development work where you need full access to file operations and system commands.

* * *

### [Plan](https://opencode.ai/docs/modes/#plan)

A restricted mode designed for planning and analysis. In plan mode, the following tools are disabled by default:

- `write` - Cannot create new files
- `edit` - Cannot modify existing files
- `patch` - Cannot apply patches
- `bash` - Cannot execute shell commands

This mode is useful when you want the AI to analyze code, suggest changes, or create plans without making any actual modifications to your codebase.

* * *

## [Switching](https://opencode.ai/docs/modes/#switching)

You can switch between modes during a session using the _Tab_ key. Or your configured `switch_mode` keybind.

* * *

## [Configure](https://opencode.ai/docs/modes/#configure)

You can customize the built-in modes or create your own in the opencode [config](https://opencode.ai/docs/config).

```

{

  "$schema": "https://opencode.ai/config.json",

  "mode": {

    "build": {

      "model": "anthropic/claude-sonnet-4-20250514",

      "prompt": "{file:./prompts/build.txt}",

      "tools": {

        "write": true,

        "edit": true,

        "bash": true

      }

    },

    "plan": {

      "model": "anthropic/claude-haiku-4-20250514",

      "tools": {

        "write": false,

        "edit": false,

        "bash": false

      }

    }

  }

}
```

Let’s look at these options in detail.

* * *

### [Model](https://opencode.ai/docs/modes/#model)

Use the `model` config to override the default model for this mode. Useful for using different models optimized for different tasks. For example, a faster model for planning, a more capable model for implementation.

```

{

  "mode": {

    "plan": {

      "model": "anthropic/claude-haiku-4-20250514"

    }

  }

}
```

* * *

### [Prompt](https://opencode.ai/docs/modes/#prompt)

Specify a custom system prompt file for this mode with the `prompt` config. The prompt file should contain instructions specific to the mode’s purpose.

```

{

  "mode": {

    "review": {

      "prompt": "{file:./prompts/code-review.txt}"

    }

  }

}
```

This path is relative to where the config file is located. So this works for
both the global opencode config and the project specific config.

* * *

### [Tools](https://opencode.ai/docs/modes/#tools)

Control which tools are available in this mode with the `tools` config. You can enable or disable specific tools by setting them to `true` or `false`.

```

{

  "mode": {

    "readonly": {

      "tools": {

        "write": false,

        "edit": false,

        "bash": false,

        "read": true,

        "grep": true,

        "glob": true

      }

    }

  }

}
```

If no tools are specified, all tools are enabled by default.

* * *

#### [Available tools](https://opencode.ai/docs/modes/#available-tools)

Here are all the tools can be controlled through the mode config.

| Tool | Description |
| --- | --- |
| `bash` | Execute shell commands |
| `edit` | Modify existing files |
| `write` | Create new files |
| `read` | Read file contents |
| `grep` | Search file contents |
| `glob` | Find files by pattern |
| `list` | List directory contents |
| `patch` | Apply patches to files |
| `todowrite` | Manage todo lists |
| `todoread` | Read todo lists |
| `webfetch` | Fetch web content |

* * *

## [Custom modes](https://opencode.ai/docs/modes/#custom-modes)

You can create your own custom modes by adding them to the `mode` configuration. For example, a documentation mode that focuses on reading and analysis.

```

{

  "$schema": "https://opencode.ai/config.json",

  "mode": {

    "docs": {

      "prompt": "{file:./prompts/documentation.txt}",

      "tools": {

        "write": true,

        "edit": true,

        "bash": false,

        "read": true,

        "grep": true,

        "glob": true

      }

    }

  }

}
```

* * *

### [Use cases](https://opencode.ai/docs/modes/#use-cases)

Here are some common use cases for different modes.

- **Build mode**: Full development work with all tools enabled
- **Plan mode**: Analysis and planning without making changes
- **Review mode**: Code review with read-only access plus documentation tools
- **Debug mode**: Focused on investigation with bash and read tools enabled
- **Docs mode**: Documentation writing with file operations but no system commands

You might also find different models are good for different use cases.

---

## Opencode AI Docs Rules

[Skip to content](https://opencode.ai/docs/rules/#_top)

# Rules

Set custom instructions for opencode.

You can provide custom instructions to opencode by creating an `AGENTS.md` file. This is similar to `CLAUDE.md` or Cursor’s rules. It contains instructions that will be included in the LLM’s context to customize its behavior for your specific project.

* * *

## [Initialize](https://opencode.ai/docs/rules/#initialize)

To create a new `AGENTS.md` file, you can run the `/init` command in opencode.

This will scan your project and all its contents to understand what the project is about and generate an `AGENTS.md` file with it. This helps opencode to navigate the project better.

If you have an existing `AGENTS.md` file, this will try to add to it.

* * *

## [Example](https://opencode.ai/docs/rules/#example)

You can also just create this file manually. Here’s an example of some things you can put into an `AGENTS.md` file.

```

# SST v3 Monorepo Project

This is an SST v3 monorepo with TypeScript. The project uses bun workspaces for package management.

## Project Structure

- `packages/` - Contains all workspace packages (functions, core, web, etc.)

- `infra/` - Infrastructure definitions split by service (storage.ts, api.ts, web.ts)

- `sst.config.ts` - Main SST configuration with dynamic imports

## Code Standards

- Use TypeScript with strict mode enabled

- Shared code goes in `packages/core/` with proper exports configuration

- Functions go in `packages/functions/`

- Infrastructure should be split into logical files in `infra/`

## Monorepo Conventions

- Import shared modules using workspace names: `@my-app/core/example`
```

We are adding project-specific instructions here and this will be shared across your team.

* * *

## [Types](https://opencode.ai/docs/rules/#types)

opencode also supports reading the `AGENTS.md` file from multiple locations. And this serves different purposes.

### [Project](https://opencode.ai/docs/rules/#project)

The ones we have seen above, where the `AGENTS.md` is placed in the project root, are project-specific rules. These only apply when you are working in this directory or its sub-directories.

### [Global](https://opencode.ai/docs/rules/#global)

You can also have global rules in a `~/.config/opencode/AGENTS.md` file. This gets applied across all opencode sessions.

Since this isn’t committed to Git or shared with your team, we recommend using this to specify any personal rules that the LLM should follow.

* * *

## [Precedence](https://opencode.ai/docs/rules/#precedence)

So when opencode starts, it looks for:

1. **Local files** by traversing up from the current directory
2. **Global file** by checking `~/.config/opencode/AGENTS.md`

If you have both global and project-specific rules, opencode will combine them together.

* * *

## [Custom Instructions](https://opencode.ai/docs/rules/#custom-instructions)

You can specify custom instruction files in your `opencode.json` or the global `~/.config/opencode/opencode.json`. This allows you and your team to reuse existing rules rather than having to duplicate them to AGENTS.md.

Example:

```

{

  "$schema": "https://opencode.ai/config.json",

  "instructions": ["CONTRIBUTING.md", "docs/guidelines.md", ".cursor/rules/*.md"]

}
```

All instruction files are combined with your `AGENTS.md` files.

---

## Opencode AI Docs Share

[Skip to content](https://opencode.ai/docs/share/#_top)

# Share

Share your opencode conversations.

opencode’s share feature allows you to create public links to your opencode conversations, so you can collaborate with teammates or get help from others.

* * *

## [How it works](https://opencode.ai/docs/share/#how-it-works)

When you share a conversation, opencode:

1. Creates a unique public URL for your session
2. Syncs your conversation history to our servers
3. Makes the conversation accessible via the shareable link — `opencode.ai/s/<share-id>`

* * *

## [Sharing](https://opencode.ai/docs/share/#sharing)

You can manually share a conversation or enable automatic sharing for all new conversations.

* * *

### [Manual](https://opencode.ai/docs/share/#manual)

Use the `/share` command in any conversation to create a shareable link:

```

/share
```

This will generate a unique URL that’ll be copied to your clipboard.

* * *

### [Autoshare](https://opencode.ai/docs/share/#autoshare)

You can enable automatic sharing for all new conversations through the `autoshare` option in your [config file](https://opencode.ai/docs/config).

```

{

  "$schema": "https://opencode.ai/config.json",

  "autoshare": true

}
```

By default, `autoshare` is disabled.

* * *

## [Unsharing](https://opencode.ai/docs/share/#unsharing)

To stop sharing a conversation and remove it from public access:

```

/unshare
```

This will remove the share link and delete the data related to the conversation.

* * *

## [Privacy](https://opencode.ai/docs/share/#privacy)

There are a few things to keep in mind when sharing a conversation.

* * *

### [Data retention](https://opencode.ai/docs/share/#data-retention)

Shared conversations remain accessible until you explicitly unshare them. This
includes:

- Full conversation history
- All messages and responses
- Session metadata

* * *

### [Recommendations](https://opencode.ai/docs/share/#recommendations)

- Only share conversations that don’t contain sensitive information
- Review conversation content before sharing
- Unshare conversations when collaboration is complete
- Avoid sharing conversations with proprietary code or confidential data

* * *

## [For enterprises](https://opencode.ai/docs/share/#for-enterprises)

For enterprise deployments, the share feature can be:

- **Self-hosted** on your own infrastructure
- **Restricted** to authenticated users only
- **Disabled** entirely for security compliance

[Learn more](https://opencode.ai/docs/enterprise) about using opencode in your organization.

---

## Opencode AI Docs Themes

[Skip to content](https://opencode.ai/docs/themes/#_top)

# Themes

Select a built-in theme or define your own.

With opencode you can select from one of several built-in themes, use a theme that adapts to your terminal theme, or define your own custom theme.

By default, opencode uses our own `opencode` theme.

* * *

## [Terminal requirements](https://opencode.ai/docs/themes/#terminal-requirements)

For themes to display correctly with their full color palette, your terminal must support **truecolor** (24-bit color). Most modern terminals support this by default, but you may need to enable it:

- **Check support**: Run `echo $COLORTERM` - it should output `truecolor` or `24bit`
- **Enable truecolor**: Set the environment variable `COLORTERM=truecolor` in your shell profile
- **Terminal compatibility**: Ensure your terminal emulator supports 24-bit color (most modern terminals like iTerm2, Alacritty, Kitty, Windows Terminal, and recent versions of GNOME Terminal do)

Without truecolor support, themes may appear with reduced color accuracy or fall back to the nearest 256-color approximation.

* * *

## [Built-in themes](https://opencode.ai/docs/themes/#built-in-themes)

opencode comes with several built-in themes.

| Name | Description |
| --- | --- |
| `system` | Adapts to your terminal’s background color |
| `tokyonight` | Based on the Tokyonight theme |
| `everforest` | Based on the Everforest theme |
| `ayu` | Based on the Ayu dark theme |
| `catppuccin` | Based on the Catppuccin theme |
| `gruvbox` | Based on the Gruvbox theme |
| `kanagawa` | Based on the Kanagawa theme |
| `nord` | Based on the Nord theme |
| `matrix` | Hacker-style green on black theme |
| `one-dark` | Based on the Atom One Dark theme |

And more, we are constantly adding new themes.

* * *

## [System theme](https://opencode.ai/docs/themes/#system-theme)

The `system` theme is designed to automatically adapt to your terminal’s color scheme. Unlike traditional themes that use fixed colors, the _system_ theme:

- **Generates gray scale**: Creates a custom gray scale based on your terminal’s background color, ensuring optimal contrast.
- **Uses ANSI colors**: Leverages standard ANSI colors (0-15) for syntax highlighting and UI elements, which respect your terminal’s color palette.
- **Preserves terminal defaults**: Uses `none` for text and background colors to maintain your terminal’s native appearance.

The system theme is for users who:

- Want opencode to match their terminal’s appearance
- Use custom terminal color schemes
- Prefer a consistent look across all terminal applications

* * *

## [Using a theme](https://opencode.ai/docs/themes/#using-a-theme)

You can select a theme by bringing up the theme select with the `/theme` command. Or you can specify it in your [config](https://opencode.ai/docs/config).

```

{

  "$schema": "https://opencode.ai/config.json",

  "theme": "tokyonight"

}
```

* * *

## [Custom themes](https://opencode.ai/docs/themes/#custom-themes)

opencode supports a flexible JSON-based theme system that allows users to create and customize themes easily.

* * *

### [Hierarchy](https://opencode.ai/docs/themes/#hierarchy)

Themes are loaded from multiple directories in the following order where later directories override earlier ones:

1. **Built-in themes** - These are embedded in the binary
2. **User config directory** - Defined in `~/.config/opencode/themes/*.json` or `$XDG_CONFIG_HOME/opencode/themes/*.json`
3. **Project root directory** - Defined in the `<project-root>/.opencode/themes/*.json`
4. **Current working directory** - Defined in `./.opencode/themes/*.json`

If multiple directories contain a theme with the same name, the theme from the directory with higher priority will be used.

* * *

### [Creating a theme](https://opencode.ai/docs/themes/#creating-a-theme)

To create a custom theme, create a JSON file in one of the theme directories.

For user-wide themes:

```

mkdir -p ~/.config/opencode/themes

vim ~/.config/opencode/themes/my-theme.json
```

And for project-specific themes.

```

mkdir -p .opencode/themes

vim .opencode/themes/my-theme.json
```

* * *

### [JSON format](https://opencode.ai/docs/themes/#json-format)

Themes use a flexible JSON format with support for:

- **Hex colors**: `"#ffffff"`
- **ANSI colors**: `3` (0-255)
- **Color references**: `"primary"` or custom definitions
- **Dark/light variants**: `{"dark": "#000", "light": "#fff"}`
- **No color**: `"none"` - Uses the terminal’s default color or transparent

* * *

### [Color definitions](https://opencode.ai/docs/themes/#color-definitions)

The `defs` section is optional and it allows you to define reusable colors that can be referenced in the theme.

* * *

### [Terminal defaults](https://opencode.ai/docs/themes/#terminal-defaults)

The special value `"none"` can be used for any color to inherit the terminal’s default color. This is particularly useful for creating themes that blend seamlessly with your terminal’s color scheme:

- `"text": "none"` - Uses terminal’s default foreground color
- `"background": "none"` - Uses terminal’s default background color

* * *

### [Example](https://opencode.ai/docs/themes/#example)

Here’s an example of a custom theme:

```

{

  "$schema": "https://opencode.ai/theme.json",

  "defs": {

    "nord0": "#2E3440",

    "nord1": "#3B4252",

    "nord2": "#434C5E",

    "nord3": "#4C566A",

    "nord4": "#D8DEE9",

    "nord5": "#E5E9F0",

    "nord6": "#ECEFF4",

    "nord7": "#8FBCBB",

    "nord8": "#88C0D0",

    "nord9": "#81A1C1",

    "nord10": "#5E81AC",

    "nord11": "#BF616A",

    "nord12": "#D08770",

    "nord13": "#EBCB8B",

    "nord14": "#A3BE8C",

    "nord15": "#B48EAD"

  },

  "theme": {

    "primary": {

      "dark": "nord8",

      "light": "nord10"

    },

    "secondary": {

      "dark": "nord9",

      "light": "nord9"

    },

    "accent": {

      "dark": "nord7",

      "light": "nord7"

    },

    "error": {

      "dark": "nord11",

      "light": "nord11"

    },

    "warning": {

      "dark": "nord12",

      "light": "nord12"

    },

    "success": {

      "dark": "nord14",

      "light": "nord14"

    },

    "info": {

      "dark": "nord8",

      "light": "nord10"

    },

    "text": {

      "dark": "nord4",

      "light": "nord0"

    },

    "textMuted": {

      "dark": "nord3",

      "light": "nord1"

    },

    "background": {

      "dark": "nord0",

      "light": "nord6"

    },

    "backgroundPanel": {

      "dark": "nord1",

      "light": "nord5"

    },

    "backgroundElement": {

      "dark": "nord1",

      "light": "nord4"

    },

    "border": {

      "dark": "nord2",

      "light": "nord3"

    },

    "borderActive": {

      "dark": "nord3",

      "light": "nord2"

    },

    "borderSubtle": {

      "dark": "nord2",

      "light": "nord3"

    },

    "diffAdded": {

      "dark": "nord14",

      "light": "nord14"

    },

    "diffRemoved": {

      "dark": "nord11",

      "light": "nord11"

    },

    "diffContext": {

      "dark": "nord3",

      "light": "nord3"

    },

    "diffHunkHeader": {

      "dark": "nord3",

      "light": "nord3"

    },

    "diffHighlightAdded": {

      "dark": "nord14",

      "light": "nord14"

    },

    "diffHighlightRemoved": {

      "dark": "nord11",

      "light": "nord11"

    },

    "diffAddedBg": {

      "dark": "#3B4252",

      "light": "#E5E9F0"

    },

    "diffRemovedBg": {

      "dark": "#3B4252",

      "light": "#E5E9F0"

    },

    "diffContextBg": {

      "dark": "nord1",

      "light": "nord5"

    },

    "diffLineNumber": {

      "dark": "nord2",

      "light": "nord4"

    },

    "diffAddedLineNumberBg": {

      "dark": "#3B4252",

      "light": "#E5E9F0"

    },

    "diffRemovedLineNumberBg": {

      "dark": "#3B4252",

      "light": "#E5E9F0"

    },

    "markdownText": {

      "dark": "nord4",

      "light": "nord0"

    },

    "markdownHeading": {

      "dark": "nord8",

      "light": "nord10"

    },

    "markdownLink": {

      "dark": "nord9",

      "light": "nord9"

    },

    "markdownLinkText": {

      "dark": "nord7",

      "light": "nord7"

    },

    "markdownCode": {

      "dark": "nord14",

      "light": "nord14"

    },

    "markdownBlockQuote": {

      "dark": "nord3",

      "light": "nord3"

    },

    "markdownEmph": {

      "dark": "nord12",

      "light": "nord12"

    },

    "markdownStrong": {

      "dark": "nord13",

      "light": "nord13"

    },

    "markdownHorizontalRule": {

      "dark": "nord3",

      "light": "nord3"

    },

    "markdownListItem": {

      "dark": "nord8",

      "light": "nord10"

    },

    "markdownListEnumeration": {

      "dark": "nord7",

      "light": "nord7"

    },

    "markdownImage": {

      "dark": "nord9",

      "light": "nord9"

    },

    "markdownImageText": {

      "dark": "nord7",

      "light": "nord7"

    },

    "markdownCodeBlock": {

      "dark": "nord4",

      "light": "nord0"

    },

    "syntaxComment": {

      "dark": "nord3",

      "light": "nord3"

    },

    "syntaxKeyword": {

      "dark": "nord9",

      "light": "nord9"

    },

    "syntaxFunction": {

      "dark": "nord8",

      "light": "nord8"

    },

    "syntaxVariable": {

      "dark": "nord7",

      "light": "nord7"

    },

    "syntaxString": {

      "dark": "nord14",

      "light": "nord14"

    },

    "syntaxNumber": {

      "dark": "nord15",

      "light": "nord15"

    },

    "syntaxType": {

      "dark": "nord7",

      "light": "nord7"

    },

    "syntaxOperator": {

      "dark": "nord9",

      "light": "nord9"

    },

    "syntaxPunctuation": {

      "dark": "nord4",

      "light": "nord0"

    }

  }

}
```

---

## Opencode AI Docs Troubleshooting

[Skip to content](https://opencode.ai/docs/troubleshooting/#_top)

# Troubleshooting

Common issues and how to resolve them.

To debug any issues with opencode, you can check the logs or the session data
that it stores locally.

* * *

### [Logs](https://opencode.ai/docs/troubleshooting/#logs)

Log files are written to:

- **macOS/Linux**: `~/.local/share/opencode/log/`
- **Windows**: `%APPDATA%\opencode\log\`

Log files are named with timestamps (e.g., `2025-01-09T123456.log`) and the most recent 10 log files are kept.

You can configure the log level in your [config file](https://opencode.ai/docs/config#logging) to get more detailed debug information.

* * *

### [Storage](https://opencode.ai/docs/troubleshooting/#storage)

opencode stores session data and other application data on disk at:

- **macOS/Linux**: `~/.local/share/opencode/`
- **Windows**: `%USERPROFILE%\.local\share\opencode`

This directory contains:

- `auth.json` - Authentication data like API keys, OAuth tokens
- `log/` - Application logs
- `project/` - Project-specific data like session and message data

  - If the project is within a Git repo, it is stored in `./<project-slug>/storage/`
  - If it is not a Git repo, it is stored in `./global/storage/`

* * *

## [Getting help](https://opencode.ai/docs/troubleshooting/#getting-help)

If you’re experiencing issues with opencode:

1. **Report issues on GitHub**

The best way to report bugs or request features is through our GitHub repository:

[**github.com/sst/opencode/issues**](https://github.com/sst/opencode/issues)

Before creating a new issue, search existing issues to see if your problem has already been reported.

2. **Join our Discord**

For real-time help and community discussion, join our Discord server:

[**opencode.ai/discord**](https://opencode.ai/discord)


* * *

## [Common issues](https://opencode.ai/docs/troubleshooting/#common-issues)

Here are some common issues and how to resolve them.

* * *

### [opencode won’t start](https://opencode.ai/docs/troubleshooting/#opencode-wont-start)

1. Check the logs for error messages
2. Try running with `--print-logs` to see output in the terminal
3. Ensure you have the latest version with `opencode upgrade`

* * *

### [Authentication issues](https://opencode.ai/docs/troubleshooting/#authentication-issues)

1. Try re-authenticating with `opencode auth login <provider>`
2. Check that your API keys are valid
3. Ensure your network allows connections to the provider’s API

* * *

### [Model not available](https://opencode.ai/docs/troubleshooting/#model-not-available)

1. Check that you’ve authenticated with the provider
2. Verify the model name in your config is correct
3. Some models may require specific access or subscriptions

* * *

### [Copy/paste not working on Linux](https://opencode.ai/docs/troubleshooting/#copypaste-not-working-on-linux)

Linux users need to have one of the following clipboard utilities installed for copy/paste functionality to work:

**For X11 systems:**

```

apt install -y xclip

# or

apt install -y xsel
```

**For Wayland systems:**

```

apt install -y wl-clipboard
```

**For headless environments:**

```

apt install -y xvfb

# and run:

Xvfb :99 -screen 0 1024x768x24 > /dev/null 2>&1 &

export DISPLAY=:99.0
```

opencode will automatically detect and use the first available clipboard tool in order of preference: `xclip`, `xsel`, then `wl-clipboard`.
