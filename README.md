
# Installing Visual Studio Code Extensions Script

This script simplifies the installation of Visual Studio Code (VSCode) extensions, ensuring that you can quickly set up your development environment with your preferred tools. It is compatible with macOS and Linux operating systems.

## Prerequisites

- Ensure you have Visual Studio Code installed on your system.
- Have Terminal access to execute shell commands.

## Installation Steps

### 1. Copy the Script
Begin by copying the script provided in the "Script" section below.

### 2. Create a Shell Script File
- Open a text editor of your choice.
- Paste the copied script into a new file.
- Save this file with a `.sh` extension, such as `install_extensions.sh`, to denote it's a shell script.

### 3. Ensure VSCode is in Your PATH
For the script to run correctly, the `code` command must be accessible from your Terminal. If it's not already, follow these steps:

1. Open Terminal.
2. Use one of the following commands to locate the Visual Studio Code application:
   ```shell
   find /Applications -name code
   ```
   or
   ```shell
   find /usr/share -name code
   ```
3. Once you have the path, add it to your shell's configuration file:
   - **Bash Users**: Append the following line to your `.bashrc` or `.bash_profile`:
     ```shell
     export PATH="/path/to/visual-studio-code/bin:$PATH"
     ```
   - **Zsh Users**: Append the following line to your `.zshrc` file:
     ```shell
     export PATH="/path/to/visual-studio-code/bin:$PATH"
     ```

### 4. Make the Script Executable
- Navigate to the directory containing your script file in Terminal.
- Run the command below to grant execution permissions:
  ```shell
  chmod +x install_extensions.sh
  ```

### 5. Execute the Script
- Run the script by typing:
  ```shell
  ./install_extensions.sh
  ```
- The script will proceed to automatically install the listed VSCode extensions.

### 6. Wait for the Installation to Complete
The script installs each extension sequentially. Wait until it finishes.

### 7. Verify the Installation
- Open VSCode and check if the new extensions are installed and available for use.

## Script
```bash
#!/bin/bash

# Extensions list
extensions=(
    "aaron-bond.better-comments"
    "batisteo.vscode-django"
    "bibhasdn.django-html"
    "bigonesystems.django"
    "boto3typed.boto3-ide"
    "chakrounanas.turbo-console-log"
    "chrmarti.regex"
    "datadog.datadog-vscode"
    "donjayamanne.githistory"
    "dracula-theme.theme-dracula"
    "eamodio.gitlens"
    "esbenp.prettier-vscode"
    "formulahendry.auto-rename-tag"
    "formulahendry.code-runner"
    "github.codespaces"
    "github.copilot"
    "github.copilot-chat"
    "github.vscode-github-actions"
    "johnpapa.vscode-peacock"
    "mhutchie.git-graph"
    "michaelcurrin.auto-commit-msg"
    "ms-python.black-formatter"
    "ms-python.debugpy"
    "ms-python.python"
    "ms-python.vscode-pylance"
    "ms-vscode.cmake-tools"
    "ms-vscode.cpptools"
    "ms-vscode.cpptools-extension-pack"
    "ms-vscode.cpptools-themes"
    "oderwat.indent-rainbow"
    "pnp.polacode"
    "sourcery.sourcery"
    "streetsidesoftware.code-spell-checker"
    "twxs.cmake"
    "uloco.theme-bluloco-dark"
    "vscode-icons-team.vscode-icons"
    "zerefdev.todo-highlighter"
    "zhuangtongfa.material-theme"
)

# Install extensions
if command -v code &> /dev/null; then
    echo "Installing extensions..."
    for extension in "${extensions[@]}"; do
        code --install-extension "$extension"
    done
    echo "All extensions installed successfully."
else
    echo "Visual Studio Code not found. Please check your installation and PATH."
fi
```

## Troubleshooting

- **Command not found**: Ensure `code` is in your PATH as described in step 3.
- **Permissions error**: Verify the script is executable as described in step 4.

For further assistance, consult the Visual Studio Code documentation or your system's user manual.
