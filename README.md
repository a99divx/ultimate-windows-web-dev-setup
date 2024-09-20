
![Windows 11 Web Development Environment](/assets/windows11-webdev-environment.png)


# The Ultimate Guide to Setting Up a Windows 11 Web Development Environment

  
Setting up a streamlined and efficient web development environment on Windows 11 doesn’t need to be overwhelming. This enhanced guide will walk you through setting up essential tools, plugins, and optimizations tailored for modern web development. We'll also introduce a more hands-on learning approach by guiding you through projects, with recommended tools for improved productivity.

> 🚀 **Ready to supercharge your Windows 11 development environment?** Fork this repository to keep track of your progress and customize your setup! 
> 
> [![Fork the Repo](https://img.shields.io/github/forks/a99divx/ultimate-windows-web-dev-setup?style=social)](https://github.com/a99divx/ultimate-windows-web-dev-setup/fork)
> [![Star the Repo](https://img.shields.io/github/stars/a99divx/ultimate-windows-web-dev-setup?style=social)](https://github.com/a99divx/ultimate-windows-web-dev-setup)
> 
> 📝 **Track Your Progress**: Use the [Issues](https://github.com/a99divx/ultimate-windows-web-dev-setup/issues) tab to create a checklist of tasks as you work through this guide.
> 
> 🔧 **Customize Your Setup**: Share your own tips and tricks by [contributing](https://github.com/a99divx/ultimate-windows-web-dev-setup/blob/main/CONTRIBUTING.md) to this guide!
> 
> 💡 **Get Help**: Join our [Discussions](https://github.com/a99divx/ultimate-windows-web-dev-setup/discussions) to ask questions and share your experiences with other developers.


## Table of Contents
  

1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
3. [Windows Subsystem for Linux (WSL)](#windows-subsystem-for-linux-wsl)
4. [Windows Terminal](#windows-terminal)
5. [Git Configuration](#git-configuration)
6. [GitHub Credentials](#github-credentials)
7. [Enhancing Your Shell with Zsh and Oh My Zsh](#enhancing-your-shell-with-zsh-and-oh-my-zsh)
8. [Node.js and NVM](#nodejs-and-nvm)
9. [Visual Studio Code](#visual-studio-code)
10. [Additional Code Editors and IDEs](#additional-code-editors-and-ides)
11. [Package Managers](#package-managers)
12. [Additional Development Tools](#additional-development-tools)
13. [Browser Extensions](#browser-extensions)
14. [Productivity Tools](#productivity-tools)
15. [AI-Powered Tools](#ai-powered-tools)
16. [Conclusion](#conclusion)
17. [Additional Resources](#additional-resources)

  

## Introduction

  

In today’s fast-paced development environment, having a fully optimized setup is crucial. This comprehensive guide will help you configure an efficient workspace with essential tools like Windows Subsystem for Linux (WSL 2), modern terminal plugins, and AI-driven coding tools. You’ll also gain hands-on experience through interactive project building, which enhances retention and practical skills.
  

## Prerequisites

  

-  **Operating System**: Windows 10 version 2004 or higher, or Windows 11
-  **User Account**: Administrative privileges
-  **Internet Access**: For downloading tools and updates
-  **GitHub Account**: Sign up [here](https://github.com/) if you don't have one

  

## Windows Subsystem for Linux (WSL)

WSL allows you to run a Linux environment directly on Windows, providing a seamless integration between Windows and Linux development environments.

### Installing WSL 2

1. Open PowerShell as Administrator and run the following command:
   ```powershell
   wsl --install
   ```
2. Restart your computer to complete the installation

### Configuring WSL

1. Launch Ubuntu from the Start menu
2. Wait for the initial setup to complete
3. Create a UNIX username and password when prompted
   - Note: The password will not be visible as you type

### Updating and Upgrading Linux

To ensure your Linux environment is up-to-date, run the following commands:

### Accessing Linux Files from Windows

  

You can access your Linux files directly from Windows:

  

1. Open File Explorer and navigate to:

  

```

\\wsl$

```

  

2. Map Network Drive:

  

- Right-click on the `Ubuntu` folder.

- Select **Map network drive**.

- Choose a drive letter (e.g., `Z:`).

- Check **Reconnect at sign-in**.

- Click **Finish**.

  

This will make your Linux home directory accessible from Windows as a network drive.

  
  

### Restarting WSL

  

If you encounter issues with WSL, you can restart it:

  

```powershell

wsl --shutdown

```

  

Then relaunch your Linux distribution.

  

### Windows-Specific Considerations

  

When using WSL, keep in mind:

  

1. File system performance: Accessing Windows files from WSL or vice versa can be slower than native file access. For best performance, keep your project files within the WSL file system.

  

2. Line endings: Windows and Linux use different line ending characters. Use a `.gitattributes` file to ensure consistent line endings across operating systems.

  

3. Path differences: Windows paths use backslashes (`\`) while Linux uses forward slashes (`/`). Be mindful of this when working with paths in your code or scripts.

  

4. Permissions: Windows and Linux have different permission models. Some operations may require elevated privileges in WSL.

  

## Windows Terminal

  

Windows Terminal provides a modern interface for command-line tools, including support for tabs, themes, and customization.

  

### Installing Windows Terminal

  

Download and install Windows Terminal from the [Microsoft Store](https://aka.ms/terminal), if not already installed.

  

### Customizing Windows Terminal

  

1. Set Default Profile:

  

- Open Windows Terminal.

- Click the **down arrow** next to the **new tab** button and select **Settings**.

- Under **Startup**, set **Default profile** to **Ubuntu**.

  

2. Set Starting Directory:

  

- In **Profiles**, select **Ubuntu**.

- Under **General**, set **Starting directory** to:

  

```

\\wsl$\Ubuntu\home\your_username

```

  

3. Customize Appearance:

  

- Explore the **Appearance** tab to change the theme, font, and background.

  

4. Install Themes:

  

- Visit [Windows Terminal Themes](https://windowsterminalthemes.dev/) to find and install new themes.

  

## Git Configuration

  

Git is an essential tool for version control in software development.

  

### Installing Git

  

Git should already be installed in your WSL distribution. If not, install it:

  

```bash

sudo  apt  install  git

```

  

### Configuring Git User Information

  

Set up your global Git configuration:

  

```bash

git  config  --global  user.name  "Your Name"

git  config  --global  user.email  "youremail@example.com"

```

  

Verify your configuration:

  

```bash

git  config  --list

```

  

## GitHub Credentials

  

Authenticate with GitHub securely to manage your repositories.

  

### Generating SSH Keys

  

1. Generate a New SSH Key:

  

```bash

ssh-keygen -t ed25519 -C "youremail@example.com"

```

  

Press `Enter` to accept the default file location and set a passphrase if desired.

  

2. Start the SSH Agent:

  

```bash

eval "$(ssh-agent -s)"

```

  

3. Add Your SSH Key:

  

```bash

ssh-add ~/.ssh/id_ed25519

```

  

### Configuring GitHub with SSH

  

1. Copy Your SSH Public Key:

  

```bash

cat ~/.ssh/id_ed25519.pub

```

  

Copy the output.

  

2. Add the Key to GitHub:

  

- Log in to your GitHub account.

- Navigate to **Settings > SSH and GPG keys**.

- Click **New SSH key**, provide a title, and paste your key.

  

### Using Personal Access Tokens

  

Alternatively, use a Personal Access Token (PAT) for HTTPS authentication:

  

1. Generate a PAT:

  

- Go to **Settings > Developer settings > Personal access tokens** on GitHub.

- Click **Generate new token**, set scopes, and generate.

  

2. Store the PAT Using Git Credential Manager:

  

Install Git Credential Manager:

  

```bash

sudo apt install git-credential-manager-core

```

  

Configure Git to use it:

  

```bash

git config --global credential.helper manager-core

```

  

## Enhancing Your Shell with Zsh and Oh My Zsh

  

Zsh offers advanced features and customization options over the default Bash shell.

  

### Installing Zsh

  

```bash

sudo  apt  install  zsh

```

  

Set Zsh as your default shell:

  

```bash

chsh  -s $(which  zsh)

```

  

### Installing Oh My Zsh

  

Oh My Zsh is a framework for managing Zsh configuration.

  

1. Install Curl (if not already installed):

  

```bash

sudo apt install curl

```

  

2. Install Oh My Zsh:

  

```bash

sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

```

  

### Adding Themes and Plugins

  

1. Select a Theme:

  

- Edit `~/.zshrc` and set the `ZSH_THEME` variable. For example:

  

```bash

ZSH_THEME="agnoster"

```

  

2. Install Powerlevel10k Theme (for an enhanced prompt):

  

```bash

git clone --depth=1  https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k

```

  

Set the theme in `~/.zshrc`:

  

```bash

ZSH_THEME="powerlevel10k/powerlevel10k"

```

  

3. Install Recommended Font:

  

Powerlevel10k recommends using a Nerd Font for the best experience. Here's how to install it:

  

a. Download a Nerd Font (e.g., MesloLGS NF):

Visit [Nerd Fonts](https://www.nerdfonts.com/font-downloads) and download MesloLGS NF.

  

b. Install the font:

- Unzip the downloaded file

- Right-click on each `.ttf` file and select "Install"

  

c. Configure your terminal to use the new font:

- Open Windows Terminal settings

- Go to your Ubuntu profile

- Under "Appearance", change the "Font face" to "MesloLGS NF"

  

4. Install Plugins:

  

- zsh-autosuggestions:

  

```bash

git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

```

  

- zsh-syntax-highlighting:

  

```bash

git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

```

  

5. Enable Plugins:

  

Edit `~/.zshrc`:

  

```bash

plugins=(git  zsh-autosuggestions  zsh-syntax-highlighting)

```

  

6. Apply Changes:

  

```bash

source ~/.zshrc

```

  

7. Configure Powerlevel10k:

  

The first time you start a new terminal after installing Powerlevel10k, it will start a configuration wizard. If it doesn't, run:

  

```bash

p10k configure

```

  

Follow the prompts to customize your prompt appearance.

  

## Node.js and NVM

  

Node.js is essential for JavaScript development, and NVM allows you to manage multiple Node.js versions.

  

### Installing NVM

  

Install NVM (Node Version Manager):

  

```bash

curl  -o-  https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash

```

  

Activate NVM:

  

```bash

export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" ||  printf %s "${XDG_CONFIG_HOME}/nvm")"

[ -s "$NVM_DIR/nvm.sh" ] && \.  "$NVM_DIR/nvm.sh"

```

  

### Installing Node.js

  

Install the latest LTS (Long-Term Support) version:

  

```bash

nvm  install  --lts

```

  

### Managing Node Versions

  

List installed Node.js versions:

  

```bash

nvm  ls

```

  

Switch between versions:

  

```bash

nvm  use <version>

```

  

For example:

  

```bash

nvm  use  14

```

  

### Setting up pnpm

  

pnpm is a fast, disk space efficient package manager that can be a great alternative to npm. It offers faster installation times and uses less disk space by utilizing a content-addressable filesystem to store all files.

  

1. Install pnpm:

  

```bash

curl -fsSL https://get.pnpm.io/install.sh | sh  -

```

  

2. Add pnpm to your path:

  

Add the following line to your `~/.zshrc` or `~/.bashrc`:

  

```bash

export PATH="$HOME/.local/share/pnpm:$PATH"

```

  

Then, reload your shell configuration:

  

```bash

source ~/.zshrc # or source ~/.bashrc

```

  

3. Verify installation:

  

```bash

pnpm --version

```

  

### Using pnpm

  

Initialize a new project:

  

```bash

pnpm  init  -y

```

  

Install dependencies:

  

```bash

pnpm  install  package-name

```

  

Install a package globally:

  

```bash

pnpm  install  -g  package-name

```

  

## Visual Studio Code

  

Visual Studio Code (VS Code) is a powerful, extensible code editor.

  

### Installing VS Code

  

Download and install VS Code from the [official website](https://code.visualstudio.com/).

  

### Configuring VS Code for WSL

  

1. Install the Remote - WSL Extension:

  

- Open VS Code.

- Go to the Extensions view (`Ctrl + Shift + X`).

- Search for **Remote - WSL** and install it.

  

2. Open a WSL Project in VS Code:

  

In your WSL terminal, navigate to your project directory and run:

  

```bash

code .

```

  

### Essential Extensions

  

- Live Server: Launch a local development server with live reload.

- Prettier - Code formatter: Enforce a consistent style.

- ESLint: Integrate ESLint for JavaScript linting.

- GitLens: Enhance Git capabilities within VS Code.

- Docker: Add support for Docker files.

- Bracket Pair Colorizer 2: Color matching brackets.

- Path Intellisense: Autocomplete filenames.

- VSCode-Icons: Enrich the file explorer with icons.

- Remote - SSH: Connect to remote servers via SSH.

  

## Additional Code Editors and IDEs

  

While VS Code is popular, other editors and Integrated Development Environments (IDEs) may better suit your needs.

  

### Cursor IDE

  

Cursor IDE is an AI-powered code editor that enhances productivity, Cursor is powered by **Stripe, GitHub, Ramp, Perplexity, and OpenAI, along with many wonderful others**.

  

1. Download Cursor IDE:

  

Visit the [Cursor IDE website](https://www.cursor.so/) to download the installer.

  

2. Install Cursor IDE:

  

Run the installer and follow the on-screen instructions.

  

3. Features:

  

- AI-assisted code completion.

- Intelligent error detection.

- Code refactoring tools.

- Code generation tools.

- And much more.

  

### Other IDEs

  

- JetBrains IntelliJ IDEA: Ideal for Java and Kotlin development.

- PyCharm: Specialized for Python projects.

- WebStorm: Excellent for JavaScript and TypeScript.

- Visual Studio: Comprehensive IDE for .NET development.

  

## Package Managers

  

Package managers simplify the installation and management of software.

  

### Chocolatey

  

Chocolatey is a Windows package manager.

  

#### Installing Chocolatey

  

1. Open PowerShell as Administrator.

  

2. Run the Installation Command:

  

```powershell

Set-ExecutionPolicy Bypass -Scope Process -Force; `

[System.Net.ServicePointManager]::SecurityProtocol = `

[System.Net.ServicePointManager]::SecurityProtocol -bor 3072; `

iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))

```

  

#### Using Chocolatey

  

- Install a Package:

  

```powershell

choco install package-name -y

```

  

- Upgrade All Packages:

  

```powershell

choco upgrade all -y

```

  

### Scoop

  

Scoop is another Windows package manager focused on simplicity.

  

#### Installing Scoop

  

1. Ensure PowerShell Execution Policy is Unrestricted:

  

```powershell

Set-ExecutionPolicy RemoteSigned -Scope CurrentUser

```

  

2. Install Scoop:

  

```powershell

iwr -useb get.scoop.sh | iex

```

  

#### Using Scoop

  

- Install a Package:

  

```powershell

scoop install package-name

```

  

- Update Packages:

  

```powershell

scoop update *

```

  

## Additional Development Tools

  

Enhance your development environment with these tools.

  

### Docker Desktop

  

Docker allows you to containerize applications.

  

#### Installing Docker Desktop

  

1. Download Docker Desktop from the [official website](https://www.docker.com/products/docker-desktop).

  

2. Install and restart your computer if prompted.

  

#### Using Docker with WSL 2

  

Docker Desktop integrates with WSL 2 for improved performance.

  

- Enable WSL 2 Backend:

  

In Docker Desktop settings, ensure **Use the WSL 2 based engine** is checked.

  

### Python and Pyenv

  

Manage multiple Python versions with Pyenv.

  

#### Installing Pyenv

  

1. Install Dependencies:

  

```bash

sudo apt update && sudo  apt  install  -y  make  build-essential  libssl-dev \

zlib1g-dev  libbz2-dev  libreadline-dev  libsqlite3-dev  wget  curl  llvm \

libncursesw5-dev  xz-utils  tk-dev  libxml2-dev  libxmlsec1-dev  libffi-dev  liblzma-dev

```

  

2. Install Pyenv:

  

```bash

curl https://pyenv.run | bash

```

  

3. Update Environment Variables:

  

Add the following to `~/.bashrc` or `~/.zshrc`:

  

```bash

export PATH="$HOME/.pyenv/bin:$PATH"

eval "$(pyenv init -)"

eval "$(pyenv virtualenv-init -)"

```

  

4. Restart Your Terminal.

  

#### Managing Python Versions

  

- List Available Versions:

  

```bash

pyenv install --list

```

  

- Install a Version:

  

```bash

pyenv install 3.9.7

```

  

- Set Global Version:

  

```bash

pyenv global 3.9.7

```

  

### Java Development Kit (JDK)

  

Set up Java development environment.

  

#### Installing JDK

  

Install OpenJDK:

  

```bash

sudo  apt  install  openjdk-17-jdk

```

  

#### Verify Installation

  

```bash

java  -version

```

  

## Browser Extensions

  

Enhance your web development workflow with these extensions.

  

- React Developer Tools: Inspect React component hierarchy.

- Redux DevTools: Debug Redux state changes.

- Vue.js devtools: Inspect Vue components.

- Postman Interceptor: Capture and send HTTP requests.

- ColorZilla: Advanced color picker.

- WhatFont: Identify fonts on web pages.

- JSON Viewer: Format JSON data.

  

## Productivity Tools

  

Boost your productivity with these applications.

  

- PowerToys: A set of utilities for power users.

- Wox Launcher: An efficient app launcher.

- Notion: Note-taking and project management.

- Figma: Collaborative design tool.

- Slack: Team communication platform.

- Microsoft Teams: Collaboration and communication.

  

## AI-Powered Tools

  

Leverage AI to enhance your development workflow.

  

### GitHub Copilot

  

GitHub Copilot is an AI pair programmer that helps you write code faster.

  

-  **Installation**:

  

Install the GitHub Copilot extension in VS Code.

  

-  **Features**:

  

- Code suggestions and completions.

- Supports multiple programming languages.

  

### Tabnine

  

Tabnine is an AI code completion for all major IDEs.

  

-  **Installation**:

  

Install the Tabnine plugin for your preferred IDE.

  

-  **Features**:

  

- Whole-line and full-function code completions.

- Learns from your codebase.

  

---

## Conclusion

  

Setting up a Windows web development environment can be a complex process, but with the right tools and configurations, it becomes a powerful and efficient workspace. This guide has provided a comprehensive walkthrough to help you set up your system tailored for web development, leveraging tools like WSL, modern terminals, package managers, code editors, and AI-powered utilities.

  

I hope you found this guide helpful and that it will help you get started with your web development journey. If you have any questions or feedback, please feel free to reach out.

  

## Additional Resources

  
  
  

- [Windows Subsystem for Linux Documentation](https://docs.microsoft.com/en-us/windows/wsl/): Official documentation for WSL.

- [Windows Terminal Documentation](https://docs.microsoft.com/en-us/windows/terminal/): Official documentation for Windows Terminal.

- [Git Documentation](https://git-scm.com/doc): Official documentation for Git.

- [GitHub Documentation](https://docs.github.com/): Official documentation for GitHub.

- [Zsh Documentation](https://zsh.sourceforge.io/Doc/): Official documentation for Zsh.

- [Oh My Zsh Documentation](https://ohmyz.sh/): Official documentation for Oh My Zsh.

- [Node.js Documentation](https://nodejs.org/en/docs/): Official documentation for Node.js.

- [NVM Documentation](https://github.com/nvm-sh/nvm#readme): Official documentation for NVM.

- [Visual Studio Code Documentation](https://code.visualstudio.com/docs): Official documentation for Visual Studio Code.

- [Chocolatey Documentation](https://docs.chocolatey.org/): Official documentation for Chocolatey.

- [Scoop Documentation](https://scoop.sh/): Official documentation for Scoop.

- [Docker Documentation](https://docs.docker.com/): Official documentation for Docker.

- [Python Documentation](https://docs.python.org/): Official documentation for Python.

- [Pyenv Documentation](https://github.com/pyenv/pyenv#readme): Official documentation for Pyenv.

- [Java Documentation](https://docs.oracle.com/en/java/): Official documentation for Java.

- [PowerToys Documentation](https://docs.microsoft.com/en-us/windows/powertoys/): Official documentation for PowerToys.

- [Wox Documentation](https://github.com/Wox-launcher/Wox/wiki): Official documentation for Wox.

- [Notion Documentation](https://www.notion.so/help): Official documentation for Notion.

- [Figma Documentation](https://help.figma.com/): Official documentation for Figma.

- [Slack Documentation](https://slack.com/help): Official documentation for Slack.

- [Microsoft Teams Documentation](https://docs.microsoft.com/en-us/microsoftteams/): Official documentation for Microsoft Teams.

- [GitHub Copilot Documentation](https://docs.github.com/en/copilot): Official documentation for GitHub Copilot.

- [Tabnine Documentation](https://www.tabnine.com/docs): Official documentation for Tabnine.

- [Codeium Documentation](https://docs.codeium.com/): Official documentation for Codeium.