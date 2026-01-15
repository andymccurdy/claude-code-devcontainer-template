# Overview 

GitHub template for creating devcontainers that work well with Claude Code

## Why do I need this?

Devcontainers provide reproducible development environments and isolate project dependencies. Running Claude Code within a devcontainer limits the [potential damage Claude Code](https://www.reddit.com/r/ClaudeAI/comments/1pgxckk/claude_cli_deleted_my_entire_home_directory_wiped/) can do to your host OS and data.

Anthropic provides a standard [devcontainer feature](https://containers.dev/implementors/features/) to install Claude Code. Claude Code stores its configuration and authentication token within the devcontainer. When the devcontainer is rebuilt (which I find happens frequently during early development), Claude Code's config is lost and requires reauthenticating.

This template uses Anthropic's devcontainer feature and additionally creates a named volume to persist Claude Code's data between container rebuilds.