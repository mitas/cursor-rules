# Cursor Rules: Opinionated Preset for Enhanced Workflows

[![Cursor Version](https://img.shields.io/badge/Cursor-v0.47.8-blue)](https://cursor.sh)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/mitas/cursor-rules/pulls)

A carefully crafted collection of rules that optimize your Cursor AI experience. These rules enforce consistent practices, improve AI assistance quality, and streamline common development workflows.

> **Note:** This is an opinionated preset designed to enhance productivity. Feel free to adapt these rules to your personal preferences! ✨

## 🚀 Quick Start

The `apply-rules.sh` script allows you to download rules directly to your project without cloning the entire repository:

```bash
# Download the script
curl -o apply-rules.sh https://raw.githubusercontent.com/mitas/cursor-rules/master/apply-rules.sh && chmod +x apply-rules.sh

# Basic usage - download rules to target directory
./apply-rules.sh /path/to/your/project

# Overwrite existing rules
./apply-rules.sh --ow /path/to/your/project
```

Parameters:

- `--ow`: Optional flag to overwrite existing rules
- `<target_directory>`: Required path where rules will be downloaded

After running the script:

1. Reindex the project, so new rules are applied.
2. Enjoy enhanced AI interactions!

## ✨ Features

- **Structured Organization** - Logically organized rules by domain and purpose
- **Improved AI Responses** - Guidelines for more helpful and consistent AI assistance
- **Development Workflows** - Optimized patterns for git, directory management, and more
- **Language-Specific Rules** - Specialized rules for Markdown and other languages
- **Customizable Framework** - Easily extend with your own rules

## 📁 Rules Organization

Rules are organized in specific directories:

| Directory   | Purpose                                         |
| ----------- | ----------------------------------------------- |
| `core/`     | Core rules for Cursor behavior and rules system |
| `local/`    | Personal rules (gitignored)                     |
| `global/`   | Rules applied to every context                  |
| `overview/` | Project overviews and descriptions              |
| `testing/`  | Testing approach guidelines                     |
| `tools/`    | OS-specific utilities and common tools          |
| `lang/`      | Language-specific rules in subdirectories       |

### Available Rules

#### Core Rules

- `core/clean-code.mdc` - Code Quality Guidelines
- `core/coding-principles.mdc` - Code Quality Principles
- `core/cursor-rules.mdc` - Cursor Rules Format
- `core/emoji-usage.mdc` - Emoji Usage Guidelines
- `core/gitflow.mdc` - Gitflow Workflow Rules

#### Tools Rules

- `tools/commit-message.mdc` - Semantic Commit Messages
- `tools/directory-listing.mdc` - Directory Listing Guidelines
- `tools/git.mdc` - Git Command Usage

#### Language-Specific Rules

- `lang/cpp/cpp.mdc` - C++ Programming Guidelines
- `lang/css/tailwind.mdc` - Tailwind CSS Best Practices
- `lang/golang/golang.mdc` - Go (Golang) Coding Standards
- `lang/golang/golang-project-structure.mdc` - Go Project Structure Best Practices
- `lang/markdown/formatting.mdc` - Markdown Formatting Standards
- `lang/node/node-express.mdc` - Node.js and Express.js Best Practices
- `lang/php/php.mdc` - PHP Coding Standards and Best Practices
- `lang/php/php-7.4.mdc` - PHP 7.4 Features and Best Practices
- `lang/php/php-8.0.mdc` - PHP 8.0 Features and Best Practices
- `lang/php/php-8.1.mdc` - PHP 8.1 Features and Best Practices
- `lang/php/php-8.2.mdc` - PHP 8.2 Features and Best Practices
- `lang/php/php-8.3.mdc` - PHP 8.3 Features and Best Practices
- `lang/php/phpunit-test.mdc` - PHPUnit Testing Best Practices
- `lang/python/fastapi.mdc` - FastAPI Best Practices
- `lang/python/python.mdc` - Python Best Practices
- `lang/react/nextjs.mdc` - Next.js Best Practices
- `lang/react/react.mdc` - React Best Practices
- `lang/sql/database.mdc` - Database Best Practices
- `lang/svelte/svelte.mdc` - Svelte Best Practices
- `lang/typescript/typescript.mdc` - TypeScript Best Practices
- `lang/vue/vue.mdc` - Vue.js Best Practices


## ⚙️ Configuration

### Editor Settings

For optimal experience with `.mdc` files and to avoid flaky behavior of Cursor's MDC editor:

```json
{
  "files.associations": {
    "*.mdc": "markdown"
  },
  "workbench.editorAssociations": {
    "*.mdc": "default"
  }
}
```

This configuration sets the default text editor for `.mdc` files and enables markdown syntax highlighting.

### `.cursorindexignore` Setup

During active development of your rules:

```
# Add to .cursorindexignore
.cursor/rules/*
```

This prevents rules from being embedded in the index while they're changing rapidly. After finalizing your rules, remove this entry and manually rebuild the index for better rule accessibility.

## 🔧 Working with Rules

### Creating New Rules

1. Just ask agent to create new rule, outlining desired properties and application plain.
2. Review and work on the rule with agent.
3. Save and commit.

### Rule Synchronization

When creating or deleting rules (excluding rules in the `overview/` directory):

1. Update the `RULES` array in the `apply-rules.sh` script to keep it synchronized
2. Follow the existing categorization structure and alphabetical order
3. Commit both the rule changes and script updates together

See the [rules-synchronization.mdc](.cursor/rules/overview/rules-synchronization.mdc) file for more details.

### After Rules Update

For Cursor to apply updated or newly created rules:

1. Restart the context so rules can be re-indexed, or
2. Explicitly specify the updated rule files for Cursor to reindex them

## 🧠 Advanced Usage

### Self-Questioning Reasoning Framework

The `.ai/meta-prompt-example.md` file provides a sample "User rule" that implements a self-questioning reasoning framework. This approach enhances the AI's problem-solving capabilities through structured internal dialogue.

> **Important:** This approach is optimized for Cursor and not recommended for other AI platforms that may bill differently based on output token usage. The self-questioning framework generates substantial output tokens which could result in higher costs on platforms with different billing models.

## 🤝 Contributing

Contributions are welcome! If you have ideas for new rules or improvements to existing ones, please:

1. Fork the repository
2. Create your feature branch
3. Submit a pull request
