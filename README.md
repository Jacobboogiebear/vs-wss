# Workspace Shared Settings

## PATCHES BY [Jacobboogiebear](https://github.com/Jacobboogiebear):

1. Removed all "Initalization" features, as to prevent popups since my tools using already have it setup

2. Transfered commands from Yarn to npm


## Features

- Have you ever need to use ${workspaceFolder} in your settings.json?
- Were you struggling to share settings with your team?
- Do you have multiple devices running different OSes and you need the same settings everywhere?

This extension is an answer to all these questions.

The long-awaited feature (since 2016 - [issue](https://github.com/Microsoft/vscode/issues/2809)) is finally here!

## Examples

```
// .vscode/settings.workspace.json
{
    // Using built-in variable:
    "java.settings.url": "${workspaceFolder}/.vscode/org.eclipse.jdt.core.prefs",

    // Using environment variable:
    "java.jdt.ls.java.home": "${env:JAVA_HOME}",

    // Using command substitution:
    "tool.root": "/usr/lib/$(tool --version)"
}
```

## Extension Settings

This extension contributes the following settings:

- none at the moment. :)

## Known Issues

This is just a proof of concept, but it already works as of today. PRs are welcome.

- Given property value `"$(echo \"Hello :)\")"` will be parsed incorrectly as `echo "Hello :` so that the execution will fail.

## Release Notes

### 0.0.4

- Added basic commands substitution with `$(command --flags)` syntax.

### 0.0.3

- Added env vars substitution with `${env:VAR_NAME}` syntax.

### 0.0.2

- Added a separate command to apply settings from `settings.workspace.json`.

### 0.0.1

- Initial release of the extension - just a proof of concept.

## TODO

- Add more substitutions.
- Ask to apply new workspace settings after changing/syncing the settings.workspace.json file.
- Show the diff between "current" and "future" settings.
- Add support for `workspace.local.json` (or `settings.local.json`) file, so that you don't need multiple extensions doing the same job.
- Show .gitignore recommendations.
- I18n.
- Tests.
