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

# Basic usage - download all rules to target directory
./apply-rules.sh /path/to/your/project

# Overwrite existing rules
./apply-rules.sh --ow /path/to/your/project

# Filter rules by pattern (e.g., only download UV-related rules)
./apply-rules.sh --filter "uv*" /path/to/your/project

# Filter multiple rule types (e.g., UV and Python rules)
./apply-rules.sh --filter "uv*|python*" /path/to/your/project
```

Parameters:

- `--ow`: Optional flag to overwrite existing rules
- `--filter PATTERN`: Optional regex pattern to filter which rules to download
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

All rules are now stored directly in the `.cursor/rules/` directory using a flat structure for simplicity and ease of management.

### Available Rules

#### Core Rules

- `clean-code.mdc` - Code Quality Guidelines
- `coding-principles.mdc` - Code Quality Principles
- `cursor-rules.mdc` - Cursor Rules Format
- `emoji-usage.mdc` - Emoji Usage Guidelines
- `gitflow.mdc` - Gitflow Workflow Rules

#### Tools Rules

- `commit-message.mdc` - Semantic Commit Messages
- `directory-listing.mdc` - Directory Listing Guidelines
- `git.mdc` - Git Command Usage

#### Language-Specific Rules

- `cpp.mdc` - C++ Programming Guidelines
- `tailwind.mdc` - Tailwind CSS Best Practices
- `golang.mdc` - Go (Golang) Coding Standards
- `golang-project-structure.mdc` - Go Project Structure Best Practices
- `formatting.mdc` - Markdown Formatting Standards
- `node-express.mdc` - Node.js and Express.js Best Practices
- `php.mdc` - PHP Coding Standards and Best Practices
- `php-7.4.mdc` - PHP 7.4 Features and Best Practices
- `php-8.0.mdc` - PHP 8.0 Features and Best Practices
- `php-8.1.mdc` - PHP 8.1 Features and Best Practices
- `php-8.2.mdc` - PHP 8.2 Features and Best Practices
- `php-8.3.mdc` - PHP 8.3 Features and Best Practices
- `phpunit-test.mdc` - PHPUnit Testing Best Practices
- `fastapi.mdc` - FastAPI Best Practices
- `python.mdc` - Python Best Practices
- `nextjs.mdc` - Next.js Best Practices
- `react.mdc` - React Best Practices
- `database.mdc` - Database Best Practices
- `svelte.mdc` - Svelte Best Practices
- `typescript.mdc` - TypeScript Best Practices
- `uv-tool-usage.mdc` - UV Python Package Manager Best Practices
- `vue.mdc` - Vue.js Best Practices


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

When creating or deleting rules:

1. Update the `RULES` array in the `apply-rules.sh` script to keep it synchronized
2. Maintain alphabetical order in the array for easy management
3. Commit both the rule changes and script updates together

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
