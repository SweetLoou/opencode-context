# OpenCode Documentation

## Introduction

[**opencode**](/) is an AI coding agent built for the terminal. It features:
- A responsive, native, themeable terminal UI.
- Automatically loads the right LSPs, so the LLMs make fewer mistakes.
- Have multiple agents working in parallel on the same project.
- Create shareable links to any session for reference or to debug.
- Log in with Anthropic to use your Claude Pro or Claude Max account.
- Supports 75+ LLM providers through [Models.dev](https://models.dev), including local models.

---

## Install

```bash
npm install -g opencode-ai
```

```bash
bun install -g opencode-ai
```

```bash
pnpm install -g opencode-ai
```

```bash
yarn global add opencode-ai
```

You can also install the opencode binary through the following.

##### Using the install script
```bash
curl -fsSL https://opencode.ai/install | bash
```

##### Using Homebrew on macOS
```bash
brew install sst/tap/opencode
```

##### Using Paru on Arch Linux
```bash
paru -S opencode-bin
```

##### Windows
Right now the automatic installation methods do not work properly on Windows. However you can grab the binary from the [Releases](https://github.com/sst/opencode/releases).

---

## Providers

We recommend signing up for Claude Pro or Max, running `opencode auth login` and selecting Anthropic. It's the most cost-effective way to use opencode.

```bash
$ opencode auth login
┌ Add credential
│ ◆ Select provider
│ ● Anthropic (recommended)
│ ○ OpenAI
│ ○ Google
│ ○ Amazon Bedrock
│ ○ Azure
│ ○ DeepSeek
│ ○ Groq
│ ...
└
```

opencode is powered by the provider list at [Models.dev](https://models.dev), so you can use `opencode auth login` to configure API keys for any provider you'd like to use. This is stored in `~/.local/share/opencode/auth.json`.

The Models.dev dataset is also used to detect common environment variables like `OPENAI_API_KEY` to autoload that provider.

If there are additional providers you want to use you can submit a PR to the [Models.dev repo](https://github.com/sst/models.dev). You can also [add them to your config](/docs/config) for yourself.

---

## CLI

Running the opencode CLI starts it for the current directory.

```bash
opencode
```

Or you can start it for a specific working directory.

```bash
opencode /path/to/project
```

---

### Commands

The opencode CLI also has the following commands.

---

#### run

Run opencode in non-interactive mode by passing a prompt directly.

```bash
opencode run [message..]
```

This is useful for scripting, automation, or when you want a quick answer without launching the full TUI. For example.

```bash
"opencode run"
opencode run Explain the use of context in Go
```

##### Flags

| Flag | Short | Description |
| --- | --- | --- |
| `--continue` | `-c` | Continue the last session |
| `--session` | `-s` | Session ID to continue |
| `--share` | | Share the session |
| `--model` | `-m` | Model to use in the form of provider/model |

---

#### auth

Command to manage credentials and login for providers.

```bash
opencode auth [command]
```

---

##### login

Logs you into a provider and saves them in the credentials file in `~/.local/share/opencode/auth.json`.

```bash
opencode auth login
```

When opencode starts up it will loads the providers from the credentials file. And if there are any keys defined in your environments or a `.env` file in your project.

---

##### list

Lists all the authenticated providers as stored in the credentials file.

```bash
opencode auth list
```

Or the short version.

```bash
opencode auth ls
```

---

##### logout

Logs you out of a provider by clearing it from the credentials file.

```bash
opencode auth logout
```

---

#### upgrade

Updates opencode to the latest version or a specific version.

```bash
opencode upgrade [target]
```

To upgrade to the latest version.

```bash
opencode upgrade
```

To upgrade to a specific version.

```bash
opencode upgrade v0.1.48
```

---

### Flags

The opencode CLI takes the following flags.

| Flag | Short | Description |
| --- | --- | --- |
| `--help` | `-h` | Display help |
| `--version` | | Print version number |
| `--print-logs` | | Print logs to stderr |

---

## Config

You can configure opencode using a JSON config file that can be placed in:
- Globally under `~/.config/opencode/config.json`.
- Your project root under `opencode.json`. This is safe to be checked into Git and uses the same schema as the global one.

```json
{
  "$schema": "https://opencode.ai/config.json",
  "theme": "opencode",
  "model": "anthropic/claude-sonnet-4-20250514",
  "autoshare": false,
  "autoupdate": true
}
```

In most cases, you'll want to use the global config for things like themes, providers, or keybinds. Having a config per project is useful if you are using different providers for your company.

When opencode starts up, it looks for a config file in the current directory or traverse up to the nearest Git directory.

---

### Schema

The config file has a schema that's defined in [**`opencode.ai/config.json`**](https://opencode.ai/config.json). Your editor should be able to validate and autocomplete based on the schema.

---

#### Models

You can configure the providers and models you want to use in your opencode config through the `provider` and `model` options.

```json
{
  "$schema": "https://opencode.ai/config.json",
  "provider": {
  },
  "model": ""
}
```

[Learn more here](/docs/models).

---

#### Themes

You can configure the theme you want to use in your opencode config through the `theme` option.

```json
{
  "$schema": "https://opencode.ai/config.json",
  "theme": ""
}
```

[Learn more here](/docs/themes).

---

#### Keybinds

You can customize your keybinds through the `keybinds` option.

```json
{
  "$schema": "https://opencode.ai/config.json",
  "keybinds": {
  }
}
```

[Learn more here](/docs/keybinds).

---

#### MCP servers

You can configure MCP servers you want to use through the `mcp` option.

```json
{
  "$schema": "https://opencode.ai/config.json",
  "mcp": {
  }
}
```

[Learn more here](/docs/mcp-servers).

---

#### Disabled providers

You can disable providers that are loaded automatically through the `disabled_providers` option. This is useful when you want to prevent certain providers from being loaded even if their credentials are available.

```json
{
  "$schema": "https://opencode.ai/config.json",
  "disabled_providers": ["openai", "gemini"]
}
```

The `disabled_providers` option accepts an array of provider IDs. When a provider is disabled:
- It won't be loaded even if environment variables are set
- It won't be loaded even if API keys are configured through `opencode auth login`
- The provider's models won't appear in the model selection list

---

## Keybinds

opencode has a list of keybinds that you can customize through the opencode config.

```json
{
  "$schema": "https://opencode.ai/config.json",
  "keybinds": {
    "leader": "ctrl+x",
    "help": "h",
    "editor_open": "e",
    "session_new": "n",
    "session_list": "l",
    "session_share": "s",
    "session_interrupt": "esc",
    "session_compact": "c",
    "tool_details": "d",
    "model_list": "m",
    "theme_list": "t",
    "project_init": "i",
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
    "app_exit": "ctrl+c,q"
  }
}
```

### Leader key

opencode uses a `leader` key for most keybinds. This avoids conflicts in your terminal. By default, `ctrl+x` is the leader key and most actions require you to first press the leader key and then the shortcut.

For example, to start a new session you first press `ctrl+x` and then press `n`.

You don't need to use a leader key for your keybinds but we recommend doing so.

---

## LSP servers

opencode integrates with _Language Server Protocol_, or LSP to improve how the LLM interacts with your codebase. LSP servers for different languages give the LLM:
- **Diagnostics**: These include things like errors and lint warnings. So the LLM can generate code that has fewer mistakes without having to run the code.
- **Quick actions**: The LSP can allow the LLM to better navigate the codebase through features like _go-to-definition_ and _find references_.

### Auto-detection

By default, opencode will **automatically detect** the languages used in your project and add the right LSP servers.

### Manual configuration

You can also manually configure LSP servers by adding them under the `lsp` section in your opencode config.

```json
{
  "lsp": {
    "go": {
      "disabled": false,
      "command": "gopls"
    },
    "typescript": {
      "disabled": false,
      "command": "typescript-language-server",
      "args": ["--stdio"]
    }
  }
}
```

---

## MCP servers

You can add external tools to opencode using the _Model Context Protocol_, or MCP. opencode supports both:
- Local servers
- And remote servers

Once added, MCP tools are automatically available to the LLM alongside built-in tools.

---

### Configure

You can define MCP servers in your opencode config under `mcp`.

#### Local

Add a local MCP servers under `mcp.localmcp`.

```json
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

#### Remote

Add a remote MCP servers under `mcp.remotemcp`.

```json
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

## Models

opencode uses the [AI SDK](https://ai-sdk.dev/) and [Models.dev](https://models.dev) to support for **75+ LLM providers** and it supports running local models.

---

### Providers

You can configure providers in your opencode config under the `provider` section.

#### Defaults

Most popular providers are preloaded by default. If you've added the credentials for a provider through `opencode auth login`, they'll be available when you start opencode.

#### Custom

You can add custom providers by specifying the npm package for the provider and the models you want to use.

```json
{
  "$schema": "https://opencode.ai/config.json",
  "provider": {
    "openrouter": {
      "npm": "@openrouter/ai-sdk-provider",
      "name": "OpenRouter",
      "options": {},
      "models": {
        "anthropic/claude-3.5-sonnet": {
          "name": "Claude 3.5 Sonnet"
        }
      }
    }
  }
}
```

#### Local

To configure a local model, specify the npm package to use and the `baseURL`.

```json
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

---

### Select a model

If you have multiple models, you can select the model you want by typing in:

```bash
/models
```

---

### Loading models

When opencode starts up, it checks for the following:
1. The model list in the opencode config.

```json
{
  "$schema": "https://opencode.ai/config.json",
  "model": "anthropic/claude-sonnet-4-20250514"
}
```

The format here is `provider/model`.
2. The last used model.
3. The first model using an internal priority.

---

## Rules

You can provide custom instructions to opencode by creating an `AGENTS.md` file. This is similar to `CLAUDE.md` or Cursor's rules. It contains instructions that will be included in the LLM's context to customize its behavior for your specific project.

---

### Initialize

To create a new `AGENTS.md` file, you can run the `/init` command in opencode.

:::tip
You should commit your project's `AGENTS.md` file to Git.
:::

This will scan your project and all its contents to understand what the project is about and generate an `AGENTS.md` file with it. This helps opencode to navigate the project better.

If you have an existing `AGENTS.md` file, this will try to add to it.

---

### Example

You can also just create this file manually. Here's an example of some things you can put into an `AGENTS.md` file.

```markdown
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

---

### Types

opencode also supports reading the `AGENTS.md` file from multiple locations. And this serves different purposes.

#### Project

The ones we have seen above, where the `AGENTS.md` is placed in the project root, are project-specific rules. These only apply when you are working in this directory or its sub-directories.

#### Global

You can also have global rules in a `~/.config/opencode/AGENTS.md` file. This gets applied across all opencode sessions. Since this isn't committed to Git or shared with your team, we recommend using this to specify any personal rules that the LLM should follow.

---

### Precedence

So when opencode starts, it looks for:
1. **Local files** by traversing up from the current directory
2. **Global file** by checking `~/.config/opencode/AGENTS.md`

If you have both global and project-specific rules, opencode will combine them together.

---

### Custom Instructions

You can also specify custom instruction files using the `instructions` configuration in your `opencode.json` or global `~/.config/opencode/config.json`:

```json
{
  "$schema": "https://opencode.ai/config.json",
  "instructions": [".cursor/rules/*.md"]
}
```

You can specify multiple files like `CONTRIBUTING.md` and `docs/guidelines.md`, and use glob patterns to match multiple files. For example, to reuse your existing Cursor rules:

```json
{
  "$schema": "https://opencode.ai/config.json",
  "instructions": [".cursor/rules/*.md"]
}
```

All instruction files are combined with your `AGENTS.md` files.

---

## Themes

With opencode you can select from one of several built-in themes, use a theme that adapts to your terminal theme, or define your own custom theme.

By default, opencode uses our own `opencode` theme.

---

### Built-in themes

opencode comes with several built-in themes.

| Name | Description |
| --- | --- |
| `system` | Adapts to your terminal's background color |
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

---

### System theme

The `system` theme is designed to automatically adapt to your terminal's color scheme. Unlike traditional themes that use fixed colors, the _system_ theme:
- **Generates gray scale**: Creates a custom gray scale based on your terminal's background color, ensuring optimal contrast.
- **Uses ANSI colors**: Leverages standard ANSI colors (0-15) for syntax highlighting and UI elements, which respect your terminal's color palette.
- **Preserves terminal defaults**: Uses `none` for text and background colors to maintain your terminal's native appearance.

The system theme is for users who:
- Want opencode to match their terminal's appearance
- Use custom terminal color schemes
- Prefer a consistent look across all terminal applications

---

### Using a theme

You can select a theme by bringing up the theme select with the `/theme` command. Or you can specify it in your [config](/docs/config).

```json
{
  "$schema": "https://opencode.ai/config.json",
  "theme": "tokyonight"
}
```

---

### Custom themes

opencode supports a flexible JSON-based theme system that allows users to create and customize themes easily.

---

#### Hierarchy

Themes are loaded from multiple directories in the following order where later directories override earlier ones:
1. **Built-in themes** - These are embedded in the binary
2. **User config directory** - Defined in `~/.config/opencode/themes/*.json` or `$XDG_CONFIG_HOME/opencode/themes/*.json`
3. **Project root directory** - Defined in the `/.opencode/themes/*.json`
4. **Current working directory** - Defined in `./.opencode/themes/*.json`

If multiple directories contain a theme with the same name, the theme from the directory with higher priority will be used.

---

#### Creating a theme

To create a custom theme, create a JSON file in one of the theme directories.

For user-wide themes:

```bash
mkdir -p ~/.config/opencode/themes
vim ~/.config/opencode/themes/my-theme.json
```

And for project-specific themes.

```bash
mkdir -p .opencode/themes
vim .opencode/themes/my-theme.json
```

---

#### JSON format

Themes use a flexible JSON format with support for:
- **Hex colors**: `"#ffffff"`
- **ANSI colors**: `3` (0-255)
- **Color references**: `"primary"` or custom definitions
- **Dark/light variants**: `{"dark": "#000", "light": "#fff"}`
- **No color**: `"none"` - Uses the terminal's default color or transparent

---

#### Color definitions

The `defs` section is optional and it allows you to define reusable colors that can be referenced in the theme.

---

#### Terminal defaults

The special value `"none"` can be used for any color to inherit the terminal's default color. This is particularly useful for creating themes that blend seamlessly with your terminal's color scheme:
- `"text": "none"` - Uses terminal's default foreground color
- `"background": "none"` - Uses terminal's default background color

---

### Example

Here's an example of a custom theme:

```json
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
    "primary": { "dark": "nord8", "light": "nord10" },
    "secondary": { "dark": "nord9", "light": "nord9" },
    "accent": { "dark": "nord7", "light": "nord7" },
    "error": { "dark": "nord11", "light": "nord11" },
    "warning": { "dark": "nord12", "light": "nord12" },
    "success": { "dark": "nord14", "light": "nord14" },
    "info": { "dark": "nord8", "light": "nord10" },
    "text": { "dark": "nord4", "light": "nord0" },
    "textMuted": { "dark": "nord3", "light": "nord1" },
    "background": { "dark": "nord0", "light": "nord6" },
    "backgroundPanel": { "dark": "nord1", "light": "nord5" },
    "backgroundElement": { "dark": "nord1", "light": "nord4" },
    "border": { "dark": "nord2", "light": "nord3" },
    "borderActive": { "dark": "nord3", "light": "nord2" },
    "borderSubtle": { "dark": "nord2", "light": "nord3" },
    "diffAdded": { "dark": "nord14", "light": "nord14" },
    "diffRemoved": { "dark": "nord11", "light": "nord11" },
    "diffContext": { "dark": "nord3", "light": "nord3" },
    "diffHunkHeader": { "dark": "nord3", "light": "nord3" },
    "diffHighlightAdded": { "dark": "nord14", "light": "nord14" },
    "diffHighlightRemoved": { "dark": "nord11", "light": "nord11" },
    "diffAddedBg": { "dark": "#3B4252", "light": "#E5E9F0" },
    "diffRemovedBg": { "dark": "#3B4252", "light": "#E5E9F0" },
    "diffContextBg": { "dark": "nord1", "light": "nord5" },
    "diffLineNumber": { "dark": "nord2", "light": "nord4" },
    "diffAddedLineNumberBg": { "dark": "#3B4252", "light": "#E5E9F0" },
    "diffRemovedLineNumberBg": { "dark": "#3B4252", "light": "#E5E9F0" },
    "markdownText": { "dark": "nord4", "light": "nord0" },
    "markdownHeading": { "dark": "nord8", "light": "nord10" },
    "markdownLink": { "dark": "nord9", "light": "nord9" },
    "markdownLinkText": { "dark": "nord7", "light": "nord7" },
    "markdownCode": { "dark": "nord14", "light": "nord14" },
    "markdownBlockQuote": { "dark": "nord3", "light": "nord3" },
    "markdownEmph": { "dark": "nord12", "light": "nord12" },
    "markdownStrong": { "dark": "nord13", "light": "nord13" },
    "markdownHorizontalRule": { "dark": "nord3", "light": "nord3" },
    "markdownListItem": { "dark": "nord8", "light": "nord10" },
    "markdownListEnumeration": { "dark": "nord7", "light": "nord7" },
    "markdownImage": { "dark": "nord9", "light": "nord9" },
    "markdownImageText": { "dark": "nord7", "light": "nord7" },
    "markdownCodeBlock": { "dark": "nord4", "light": "nord0" },
    "syntaxComment": { "dark": "nord3", "light": "nord3" },
    "syntaxKeyword": { "dark": "nord9", "light": "nord9" },
    "syntaxFunction": { "dark": "nord8", "light": "nord8" },
    "syntaxVariable": { "dark": "nord7", "light": "nord7" },
    "syntaxString": { "dark": "nord14", "light": "nord14" },
    "syntaxNumber": { "dark": "nord15", "light": "nord15" },
    "syntaxType": { "dark": "nord7", "light": "nord7" },
    "syntaxOperator": { "dark": "nord9", "light": "nord9" },
    "syntaxPunctuation": { "dark": "nord4", "light": "nord0" }
  }
}
