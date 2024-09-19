# The Ultimate Guide to Setting Up a Windows Web Development Environment

Setting up a comprehensive and efficient web development environment on Windows can be a daunting task. This guide aims to streamline the process by providing step-by-step instructions on configuring your system with essential tools and optimizations needed for modern web development. We'll also touch on some AI-powered tools, including options for macOS users.

---

## Table of Contents

- [The Ultimate Guide to Setting Up a Windows Web Development Environment](#the-ultimate-guide-to-setting-up-a-windows-web-development-environment)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Prerequisites](#prerequisites)
  - [Windows Subsystem for Linux (WSL)](#windows-subsystem-for-linux-wsl)
    - [Installing WSL 2](#installing-wsl-2)
    - [Updating Linux](#updating-linux)
    - [Accessing Linux Files from Windows](#accessing-linux-files-from-windows)
    - [Restarting WSL](#restarting-wsl)
  - [Windows Terminal](#windows-terminal)
    - [Installing Windows Terminal](#installing-windows-terminal)
    - [Customizing Windows Terminal](#customizing-windows-terminal)
  - [Git Configuration](#git-configuration)
    - [Installing Git](#installing-git)
    - [Configuring Git User Information](#configuring-git-user-information)
  - [GitHub Credentials](#github-credentials)
    - [Generating SSH Keys](#generating-ssh-keys)
    - [Configuring GitHub with SSH](#configuring-github-with-ssh)
    - [Using Personal Access Tokens](#using-personal-access-tokens)
  - [Enhancing Your Shell with Zsh and](#enhancing-your-shell-with-zsh-and)
    - [Installing Zsh](#installing-zsh)
    - [Installing Oh My Zsh](#installing-oh-my-zsh)
    - [Adding Themes and Plugins](#adding-themes-and-plugins)
  - [Node.js and NVM](#nodejs-and-nvm)
    - [Installing NVM](#installing-nvm)
    - [Installing Node.js](#installing-nodejs)
    - [Managing Node Versions](#managing-node-versions)
    - [NPM Basics](#npm-basics)
  - [Visual Studio Code](#visual-studio-code)
    - [Installing VS Code](#installing-vs-code)
    - [Configuring VS Code for WSL](#configuring-vs-code-for-wsl)
    - [Essential Extensions](#essential-extensions)
  - [Additional Code Editors and IDEs](#additional-code-editors-and-ides)
    - [Cursor IDE](#cursor-ide)
    - [Other IDEs](#other-ides)
  - [Package Managers](#package-managers)
    - [Chocolatey](#chocolatey)
      - [Installing Chocolatey](#installing-chocolatey)
      - [Using Chocolatey](#using-chocolatey)
    - [Scoop](#scoop)
      - [Installing Scoop](#installing-scoop)
      - [Using Scoop](#using-scoop)
  - [Additional Development Tools](#additional-development-tools)
    - [Docker Desktop](#docker-desktop)
      - [Installing Docker Desktop](#installing-docker-desktop)
      - [Using Docker with WSL 2](#using-docker-with-wsl-2)
    - [Python and Pyenv](#python-and-pyenv)
      - [Installing Pyenv](#installing-pyenv)
      - [Managing Python Versions](#managing-python-versions)
    - [Java Development Kit (JDK)](#java-development-kit-jdk)
      - [Installing JDK](#installing-jdk)
      - [Verify Installation](#verify-installation)
  - [Browser Extensions](#browser-extensions)
  - [Productivity Tools](#productivity-tools)
  - [AI-Powered Tools](#ai-powered-tools)
    - [Wrap Terminal (macOS)](#wrap-terminal-macos)
    - [Other AI Tools](#other-ai-tools)
  - [Conclusion](#conclusion)
  - [Additional Resources](#additional-resources)
    - [Configuring WSL](#configuring-wsl)
    - [Updating Linux](#updating-linux-1)
    - [Accessing Linux Files from Windows](#accessing-linux-files-from-windows-1)
    - [Restarting WSL](#restarting-wsl-1)
  - [Windows Terminal](#windows-terminal-1)
    - [Installing Windows Terminal](#installing-windows-terminal-1)
    - [Customizing Windows Terminal](#customizing-windows-terminal-1)
  - [Git Configuration](#git-configuration-1)
    - [Installing Git](#installing-git-1)
    - [Configuring Git User Information](#configuring-git-user-information-1)
  - [GitHub Credentials](#github-credentials-1)
    - [Generating SSH Keys](#generating-ssh-keys-1)
    - [Configuring GitHub with SSH](#configuring-github-with-ssh-1)
    - [Using Personal Access Tokens](#using-personal-access-tokens-1)
  - [Enhancing Your Shell with Zsh and](#enhancing-your-shell-with-zsh-and-1)
    - [Installing Zsh](#installing-zsh-1)
    - [Installing Oh My Zsh](#installing-oh-my-zsh-1)
    - [Adding Themes and Plugins](#adding-themes-and-plugins-1)
  - [Node.js and NVM](#nodejs-and-nvm-1)
    - [Installing NVM](#installing-nvm-1)
    - [Installing Node.js](#installing-nodejs-1)
    - [Managing Node Versions](#managing-node-versions-1)
    - [NPM Basics](#npm-basics-1)
  - [Visual Studio Code](#visual-studio-code-1)
    - [Installing VS Code](#installing-vs-code-1)
    - [Configuring VS Code for WSL](#configuring-vs-code-for-wsl-1)
    - [Essential Extensions](#essential-extensions-1)
  - [Additional Code Editors and IDEs](#additional-code-editors-and-ides-1)
    - [Cursor IDE](#cursor-ide-1)
    - [Other IDEs](#other-ides-1)
  - [Package Managers](#package-managers-1)
    - [Chocolatey](#chocolatey-1)
      - [Installing Chocolatey](#installing-chocolatey-1)
      - [Using Chocolatey](#using-chocolatey-1)
    - [Scoop](#scoop-1)
      - [Installing Scoop](#installing-scoop-1)
      - [Using Scoop](#using-scoop-1)
  - [Additional Development Tools](#additional-development-tools-1)
    - [Docker Desktop](#docker-desktop-1)
      - [Installing Docker Desktop](#installing-docker-desktop-1)
      - [Using Docker with WSL 2](#using-docker-with-wsl-2-1)
    - [Python and Pyenv](#python-and-pyenv-1)
      - [Installing Pyenv](#installing-pyenv-1)
      - [Managing Python Versions](#managing-python-versions-1)
    - [Java Development Kit (JDK)](#java-development-kit-jdk-1)
      - [Installing JDK](#installing-jdk-1)
      - [Verify Installation](#verify-installation-1)
  - [Browser Extensions](#browser-extensions-1)
  - [Productivity Tools](#productivity-tools-1)
  - [AI-Powered Tools](#ai-powered-tools-1)
    - [Wrap Terminal (macOS)](#wrap-terminal-macos-1)
    - [Other AI Tools](#other-ai-tools-1)
  - [Conclusion](#conclusion-1)
  - [Additional Resources](#additional-resources-1)

---

## Introduction

In today's fast-paced tech landscape, having a well-configured development environment is crucial for productivity and efficiency. This guide provides a comprehensive walkthrough to set up a Windows machine tailored for web development, leveraging tools like Windows Subsystem for Linux (WSL), modern terminals, package managers, code editors, and AI-powered utilities.

---

## Prerequisites

- **Operating System**: Windows 10 version 2004 or higher, or Windows 11.
- **User Account**: Administrative privileges are required for installing software.
- **Internet Access**: Necessary for downloading tools and updates.
- **GitHub Account**: Sign up [here](https://github.com/) if you don't have one.

---

## Windows Subsystem for Linux (WSL)

The Windows Subsystem for Linux allows you to run a Linux environment directly on Windows without the overhead of a virtual machine, enabling you to use Linux command-line tools and utilities.

### Installing WSL 2

1. **Open PowerShell as Administrator**:

   Press `Win + X`, then select **Windows PowerShell (Admin)**.

2. **Run the Installation Command**:

   ```powershell
   wsl --install


   This command will:

   - Enable the necessary virtual machine features.
   - Download and install the latest Linux kernel.
   - Set WSL 2 as the default version.
   - Install the Ubuntu distribution.

3. **Restart Your Computer**:

   After the installation completes, restart your system to apply the changes.

### Configuring WSL

1. **Launch Ubuntu**:

   After rebooting, launch the **Ubuntu** app from the Start menu.

2. **Create a UNIX Username and Password**:

   You'll be prompted to create a new UNIX user. This account is separate from your Windows user account.

   ```bash
   Enter new UNIX username: your_username
   Enter new UNIX password:
   ```

   > **Note**: The password won't be displayed as you type.

### Updating Linux

It's essential to keep your Linux distribution up to date:

```bash
sudo apt update && sudo apt upgrade -y
```

### Accessing Linux Files from Windows

You can access your Linux files directly from Windows:

1. **Open File Explorer** and navigate to:

   ```
   \\wsl$\Ubuntu\home\your_username
   ```

2. **Map Network Drive**:

   - Right-click on the `Ubuntu` folder.
   - Select **Map network drive**.
   - Choose a drive letter (e.g., `Z:`).
   - Check **Reconnect at sign-in**.
   - Click **Finish**.

   This will make your Linux home directory accessible from Windows as a network drive.

![Mapping Network Drive](images/mapping_network_drive.png)

### Restarting WSL

If you encounter issues with WSL, you can restart it:

```powershell
wsl --shutdown
```

Then relaunch your Linux distribution.

---

## Windows Terminal

Windows Terminal provides a modern interface for command-line tools, including support for tabs, themes, and customization.

### Installing Windows Terminal

Download and install Windows Terminal from the [Microsoft Store](https://aka.ms/terminal).

### Customizing Windows Terminal

1. **Set Default Profile**:

   - Open Windows Terminal.
   - Click the **down arrow** next to the **new tab** button and select **Settings**.
   - Under **Startup**, set **Default profile** to **Ubuntu**.

2. **Set Starting Directory**:

   - In **Profiles**, select **Ubuntu**.
   - Under **General**, set **Starting directory** to:

     ```
     \\wsl$\Ubuntu\home\your_username
     ```

3. **Customize Appearance**:

   - Explore the **Appearance** tab to change the theme, font, and background.

4. **Install Themes**:

   - Visit [Windows Terminal Themes](https://windowsterminalthemes.dev/) to find and install new themes.

---

## Git Configuration

Git is an essential tool for version control in software development.

### Installing Git

Git should already be installed in your WSL distribution. If not, install it:

```bash
sudo apt install git
```

### Configuring Git User Information

Set up your global Git configuration:

```bash
git config --global user.name "Your Name"
git config --global user.email "youremail@example.com"
```

Verify your configuration:

```bash
git config --list
```

---

## GitHub Credentials

Authenticate with GitHub securely to manage your repositories.

### Generating SSH Keys

1. **Generate a New SSH Key**:

   ```bash
   ssh-keygen -t ed25519 -C "youremail@example.com"
   ```

   Press `Enter` to accept the default file location and set a passphrase if desired.

2. **Start the SSH Agent**:

   ```bash
   eval "$(ssh-agent -s)"
   ```

3. **Add Your SSH Key**:

   ```bash
   ssh-add ~/.ssh/id_ed25519
   ```

### Configuring GitHub with SSH

1. **Copy Your SSH Public Key**:

   ```bash
   cat ~/.ssh/id_ed25519.pub
   ```

   Copy the output.

2. **Add the Key to GitHub**:

   - Log in to your GitHub account.
   - Navigate to **Settings > SSH and GPG keys**.
   - Click **New SSH key**, provide a title, and paste your key.

### Using Personal Access Tokens

Alternatively, use a Personal Access Token (PAT) for HTTPS authentication:

1. **Generate a PAT**:

   - Go to **Settings > Developer settings > Personal access tokens** on GitHub.
   - Click **Generate new token**, set scopes, and generate.

2. **Store the PAT Using Git Credential Manager**:

   Install Git Credential Manager:

   ```bash
   sudo apt install git-credential-manager-core
   ```

   Configure Git to use it:

   ```bash
   git config --global credential.helper manager-core
   ```

---

## Enhancing Your Shell with Zsh and

 Oh My Zsh

Zsh offers advanced features and customization options over the default Bash shell.

### Installing Zsh

```bash
sudo apt install zsh
```

Set Zsh as your default shell:

```bash
chsh -s $(which zsh)
```

### Installing Oh My Zsh

Oh My Zsh is a framework for managing Zsh configuration.

1. **Install Curl** (if not already installed):

   ```bash
   sudo apt install curl
   ```

2. **Install Oh My Zsh**:

   ```bash
   sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
   ```

### Adding Themes and Plugins

1. **Select a Theme**:

   - Edit `~/.zshrc` and set the `ZSH_THEME` variable. For example:

     ```bash
     ZSH_THEME="agnoster"
     ```

2. **Install Powerlevel10k Theme** (for an enhanced prompt):

   ```bash
   git clone --depth=1 https://github.com/romkatv/powerlevel10k.git \
   ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
   ```

   Set the theme in `~/.zshrc`:

   ```bash
   ZSH_THEME="powerlevel10k/powerlevel10k"
   ```

3. **Install Plugins**:

   - **zsh-autosuggestions**:

     ```bash
     git clone https://github.com/zsh-users/zsh-autosuggestions \
     ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
     ```

   - **zsh-syntax-highlighting**:

     ```bash
     git clone https://github.com/zsh-users/zsh-syntax-highlighting.git \
     ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
     ```

4. **Enable Plugins**:

   Edit `~/.zshrc`:

   ```bash
   plugins=(git zsh-autosuggestions zsh-syntax-highlighting)
   ```

5. **Apply Changes**:

   ```bash
   source ~/.zshrc
   ```

---

## Node.js and NVM

Node.js is essential for JavaScript development, and NVM allows you to manage multiple Node.js versions.

### Installing NVM

Install NVM (Node Version Manager):

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
```

Activate NVM:

```bash
export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
```

### Installing Node.js

Install the latest LTS (Long-Term Support) version:

```bash
nvm install --lts
```

### Managing Node Versions

List installed Node.js versions:

```bash
nvm ls
```

Switch between versions:

```bash
nvm use <version>
```

For example:

```bash
nvm use 14
```

### NPM Basics

Initialize a new Node.js project:

```bash
npm init -y
```

Install dependencies:

```bash
npm install package-name
```

Install a package globally:

```bash
npm install -g package-name
```

---

## Visual Studio Code

Visual Studio Code (VS Code) is a powerful, extensible code editor.

### Installing VS Code

Download and install VS Code from the [official website](https://code.visualstudio.com/).

### Configuring VS Code for WSL

1. **Install the Remote - WSL Extension**:

   - Open VS Code.
   - Go to the Extensions view (`Ctrl + Shift + X`).
   - Search for **Remote - WSL** and install it.

2. **Open a WSL Project in VS Code**:

   In your WSL terminal, navigate to your project directory and run:

   ```bash
   code .
   ```

### Essential Extensions

- **Live Server**: Launch a local development server with live reload.
- **Prettier - Code formatter**: Enforce a consistent style.
- **ESLint**: Integrate ESLint for JavaScript linting.
- **GitLens**: Enhance Git capabilities within VS Code.
- **Docker**: Add support for Docker files.
- **Bracket Pair Colorizer 2**: Color matching brackets.
- **Path Intellisense**: Autocomplete filenames.
- **VSCode-Icons**: Enrich the file explorer with icons.
- **Remote - SSH**: Connect to remote servers via SSH.

---

## Additional Code Editors and IDEs

While VS Code is popular, other editors and Integrated Development Environments (IDEs) may better suit your needs.

### Cursor IDE

**Cursor IDE** is an AI-powered code editor that enhances productivity.

1. **Download Cursor IDE**:

   Visit the [Cursor IDE website](https://www.cursor.so/) to download the installer.

2. **Install Cursor IDE**:

   Run the installer and follow the on-screen instructions.

3. **Features**:

   - AI-assisted code completion.
   - Intelligent error detection.
   - Code refactoring tools.

### Other IDEs

- **JetBrains IntelliJ IDEA**: Ideal for Java and Kotlin development.
- **PyCharm**: Specialized for Python projects.
- **WebStorm**: Excellent for JavaScript and TypeScript.
- **Visual Studio**: Comprehensive IDE for .NET development.

---

## Package Managers

Package managers simplify the installation and management of software.

### Chocolatey

Chocolatey is a Windows package manager.

#### Installing Chocolatey

1. **Open PowerShell as Administrator**.

2. **Run the Installation Command**:

   ```powershell
   Set-ExecutionPolicy Bypass -Scope Process -Force; `
   [System.Net.ServicePointManager]::SecurityProtocol = `
   [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; `
   iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
   ```

#### Using Chocolatey

- **Install a Package**:

  ```powershell
  choco install package-name -y
  ```

- **Upgrade All Packages**:

  ```powershell
  choco upgrade all -y
  ```

### Scoop

Scoop is another Windows package manager focused on simplicity.

#### Installing Scoop

1. **Ensure PowerShell Execution Policy is Unrestricted**:

   ```powershell
   Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
   ```

2. **Install Scoop**:

   ```powershell
   iwr -useb get.scoop.sh | iex
   ```

#### Using Scoop

- **Install a Package**:

  ```powershell
  scoop install package-name
  ```

- **Update Packages**:

  ```powershell
  scoop update *
  ```

---

## Additional Development Tools

Enhance your development environment with these tools.

### Docker Desktop

Docker allows you to containerize applications.

#### Installing Docker Desktop

1. **Download Docker Desktop** from the [official website](https://www.docker.com/products/docker-desktop).

2. **Install** and **restart your computer** if prompted.

#### Using Docker with WSL 2

Docker Desktop integrates with WSL 2 for improved performance.

- **Enable WSL 2 Backend**:

  In Docker Desktop settings, ensure **Use the WSL 2 based engine** is checked.

### Python and Pyenv

Manage multiple Python versions with Pyenv.

#### Installing Pyenv

1. **Install Dependencies**:

   ```bash
   sudo apt update && sudo apt install -y make build-essential libssl-dev \
   zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm \
   libncursesw5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev libffi-dev liblzma-dev
   ```

2. **Install Pyenv**:

   ```bash
   curl https://pyenv.run | bash
   ```

3. **Update Environment Variables**:

   Add the following to `~/.bashrc` or `~/.zshrc`:

   ```bash
   export PATH="$HOME/.pyenv/bin:$PATH"
   eval "$(pyenv init -)"
   eval "$(pyenv virtualenv-init -)"
   ```

4. **Restart Your Terminal**.

#### Managing Python Versions

- **List Available Versions**:

  ```bash
  pyenv install --list
  ```

- **Install a Version**:

  ```bash
  pyenv install 3.9.7
  ```

- **Set Global Version**:

  ```bash
  pyenv global 3.9.7
  ```

### Java Development Kit (JDK)

Set up Java development environment.

#### Installing JDK

Install OpenJDK:

```bash
sudo apt install openjdk-17-jdk
```

#### Verify Installation

```bash
java -version
```

---

## Browser Extensions

Enhance your web development workflow with these extensions.

- **React Developer Tools**: Inspect React component hierarchy.
- **Redux DevTools**: Debug Redux state changes.
- **Vue.js devtools**: Inspect Vue components.
- **Postman Interceptor**: Capture and send HTTP requests.
- **ColorZilla**: Advanced color picker.
- **WhatFont**: Identify fonts on web pages.
-

 **JSON Viewer**: Format JSON data.

---

## Productivity Tools

Boost your productivity with these applications.

- **PowerToys**: A set of utilities for power users.
- **Wox Launcher**: An efficient app launcher.
- **Notion**: Note-taking and project management.
- **Figma**: Collaborative design tool.
- **Slack**: Team communication platform.
- **Microsoft Teams**: Collaboration and communication.

---

## AI-Powered Tools

Leverage AI to enhance your development workflow.

### Wrap Terminal (macOS)

**Wrap** is an AI-powered terminal assistant for macOS users.

1. **Download Wrap**:

   Visit the [Wrap website](https://www.wrapwithus.com/) to download the application.

2. **Install Wrap**:

   Follow the installation instructions provided on the website.

3. **Features**:

   - Natural language command execution.
   - Intelligent command suggestions.
   - Error detection and correction.

### Other AI Tools

- **GitHub Copilot**: AI pair programmer that helps you write code faster.

  - **Installation**:

    Install the GitHub Copilot extension in VS Code.

  - **Features**:

    - Code suggestions and completions.
    - Supports multiple programming languages.

- **TabNine**: AI code completion for all major IDEs.

  - **Installation**:

    Install the TabNine plugin for your preferred IDE.

  - **Features**:

    - Whole-line and full-function code completions.
    - Learns from your codebase.

---

## Conclusion

Setting up a Windows development environment with the right tools and configurations can significantly enhance your productivity. By following this guide, you now have a robust setup ready for modern web development. Keep exploring and customizing your environment to suit your workflow. Don't forget to leverage AI-powered tools to further boost your efficiency.

---

## Additional Resources

- [Microsoft Docs - WSL](https://docs.microsoft.com/windows/wsl/)
- [Oh My Zsh Documentation](https://ohmyz.sh/)
- [Node Version Manager GitHub](https://github.com/nvm-sh/nvm)
- [Visual Studio Code Extensions Marketplace](https://marketplace.visualstudio.com/VSCode)
- [Docker Documentation](https://docs.docker.com/)
- [Pyenv GitHub](https://github.com/pyenv/pyenv)
- [Chocolatey Packages](https://community.chocolatey.org/packages)
- [Scoop Buckets](https://github.com/ScoopInstaller/Main)
- [Cursor IDE](https://www.cursor.so/)
- [Wrap Terminal](https://www.wrapwithus.com/)
- [GitHub Copilot](https://github.com/features/copilot)
- [TabNine](https://www.tabnine.com/)

---

*For more projects and resources, visit my [GitHub repository](https://github.com/a99divx).*
```

Here is the enhanced article based on your outline, incorporating all the elements you specified:

```markdown
# The Ultimate Guide to Setting Up a Windows Web Development Environment

Setting up a comprehensive and efficient web development environment on Windows can be a daunting task. This guide aims to streamline the process by providing step-by-step instructions on configuring your system with essential tools and optimizations needed for modern web development. We'll also touch on some AI-powered tools, including options for macOS users.

---

## Table of Contents

1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
3. [Windows Subsystem for Linux (WSL)](#windows-subsystem-for-linux-wsl)
   - [Installing WSL 2](#installing-wsl-2)
   - [Configuring WSL](#configuring-wsl)
   - [Updating Linux](#updating-linux)
   - [Accessing Linux Files from Windows](#accessing-linux-files-from-windows)
   - [Restarting WSL](#restarting-wsl)
4. [Windows Terminal](#windows-terminal)
   - [Installing Windows Terminal](#installing-windows-terminal)
   - [Customizing Windows Terminal](#customizing-windows-terminal)
5. [Git Configuration](#git-configuration)
   - [Installing Git](#installing-git)
   - [Configuring Git User Information](#configuring-git-user-information)
6. [GitHub Credentials](#github-credentials)
   - [Generating SSH Keys](#generating-ssh-keys)
   - [Configuring GitHub with SSH](#configuring-github-with-ssh)
   - [Using Personal Access Tokens](#using-personal-access-tokens)
7. [Enhancing Your Shell with Zsh and Oh My Zsh](#enhancing-your-shell-with-zsh-and-oh-my-zsh)
   - [Installing Zsh](#installing-zsh)
   - [Installing Oh My Zsh](#installing-oh-my-zsh)
   - [Adding Themes and Plugins](#adding-themes-and-plugins)
8. [Node.js and NVM](#nodejs-and-nvm)
   - [Installing NVM](#installing-nvm)
   - [Installing Node.js](#installing-nodejs)
   - [Managing Node Versions](#managing-node-versions)
   - [NPM Basics](#npm-basics)
9. [Visual Studio Code](#visual-studio-code)
   - [Installing VS Code](#installing-vs-code)
   - [Configuring VS Code for WSL](#configuring-vs-code-for-wsl)
   - [Essential Extensions](#essential-extensions)
10. [Additional Code Editors and IDEs](#additional-code-editors-and-ides)
    - [Cursor IDE](#cursor-ide)
    - [Other IDEs](#other-ides)
11. [Package Managers](#package-managers)
    - [Chocolatey](#chocolatey)
    - [Scoop](#scoop)
12. [Additional Development Tools](#additional-development-tools)
    - [Docker Desktop](#docker-desktop)
    - [Python and Pyenv](#python-and-pyenv)
    - [Java Development Kit (JDK)](#java-development-kit-jdk)
13. [Browser Extensions](#browser-extensions)
14. [Productivity Tools](#productivity-tools)
15. [AI-Powered Tools](#ai-powered-tools)
    - [Wrap Terminal (macOS)](#wrap-terminal-macos)
    - [Other AI Tools](#other-ai-tools)
16. [Conclusion](#conclusion)
17. [Additional Resources](#additional-resources)

---

## Introduction

In today's fast-paced tech landscape, having a well-configured development environment is crucial for productivity and efficiency. This guide provides a comprehensive walkthrough to set up a Windows machine tailored for web development, leveraging tools like Windows Subsystem for Linux (WSL), modern terminals, package managers, code editors, and AI-powered utilities.

---

## Prerequisites

- **Operating System**: Windows 10 version 2004 or higher, or Windows 11.
- **User Account**: Administrative privileges are required for installing software.
- **Internet Access**: Necessary for downloading tools and updates.
- **GitHub Account**: Sign up [here](https://github.com/) if you don't have one.

---

## Windows Subsystem for Linux (WSL)

The Windows Subsystem for Linux allows you to run a Linux environment directly on Windows without the overhead of a virtual machine, enabling you to use Linux command-line tools and utilities.

### Installing WSL 2

1. **Open PowerShell as Administrator**:

   Press `Win + X`, then select **Windows PowerShell (Admin)**.

2. **Run the Installation Command**:

   ```powershell
   wsl --install
   ```

   This command will:

   - Enable the necessary virtual machine features.
   - Download and install the latest Linux kernel.
   - Set WSL 2 as the default version.
   - Install the Ubuntu distribution.

3. **Restart Your Computer**:

   After the installation completes, restart your system to apply the changes.

### Configuring WSL

1. **Launch Ubuntu**:

   After rebooting, launch the **Ubuntu** app from the Start menu.

2. **Create a UNIX Username and Password**:

   You'll be prompted to create a new UNIX user. This account is separate from your Windows user account.

   ```bash
   Enter new UNIX username: your_username
   Enter new UNIX password:
   ```

   > **Note**: The password won't be displayed as you type.

### Updating Linux

It's essential to keep your Linux distribution up to date:

```bash
sudo apt update && sudo apt upgrade -y
```

### Accessing Linux Files from Windows

You can access your Linux files directly from Windows:

1. **Open File Explorer** and navigate to:

   ```
   \\wsl$\Ubuntu\home\your_username
   ```

2. **Map Network Drive**:

   - Right-click on the `Ubuntu` folder.
   - Select **Map network drive**.
   - Choose a drive letter (e.g., `Z:`).
   - Check **Reconnect at sign-in**.
   - Click **Finish**.

   This will make your Linux home directory accessible from Windows as a network drive.

![Mapping Network Drive](images/mapping_network_drive.png)

### Restarting WSL

If you encounter issues with WSL, you can restart it:

```powershell
wsl --shutdown
```

Then relaunch your Linux distribution.

---

## Windows Terminal

Windows Terminal provides a modern interface for command-line tools, including support for tabs, themes, and customization.

### Installing Windows Terminal

Download and install Windows Terminal from the [Microsoft Store](https://aka.ms/terminal).

### Customizing Windows Terminal

1. **Set Default Profile**:

   - Open Windows Terminal.
   - Click the **down arrow** next to the **new tab** button and select **Settings**.
   - Under **Startup**, set **Default profile** to **Ubuntu**.

2. **Set Starting Directory**:

   - In **Profiles**, select **Ubuntu**.
   - Under **General**, set **Starting directory** to:

     ```
     \\wsl$\Ubuntu\home\your_username
     ```

3. **Customize Appearance**:

   - Explore the **Appearance** tab to change the theme, font, and background.

4. **Install Themes**:

   - Visit [Windows Terminal Themes](https://windowsterminalthemes.dev/) to find and install new themes.

---

## Git Configuration

Git is an essential tool for version control in software development.

### Installing Git

Git should already be installed in your WSL distribution. If not, install it:

```bash
sudo apt install git
```

### Configuring Git User Information

Set up your global Git configuration:

```bash
git config --global user.name "Your Name"
git config --global user.email "youremail@example.com"
```

Verify your configuration:

```bash
git config --list
```

---

## GitHub Credentials

Authenticate with GitHub securely to manage your repositories.

### Generating SSH Keys

1. **Generate a New SSH Key**:

   ```bash
   ssh-keygen -t ed25519 -C "youremail@example.com"
   ```

   Press `Enter` to accept the default file location and set a passphrase if desired.

2. **Start the SSH Agent**:

   ```bash
   eval "$(ssh-agent -s)"
   ```

3. **Add Your SSH Key**:

   ```bash
   ssh-add ~/.ssh/id_ed25519
   ```

### Configuring GitHub with SSH

1. **Copy Your SSH Public Key**:

   ```bash
   cat ~/.ssh/id_ed25519.pub
   ```

   Copy the output.

2. **Add the Key to GitHub**:

   - Log in to your GitHub account.
   - Navigate to **Settings > SSH and GPG keys**.
   - Click **New SSH key**, provide a title, and paste your key.

### Using Personal Access Tokens

Alternatively, use a Personal Access Token (PAT) for HTTPS authentication:

1. **Generate a PAT**:

   - Go to **Settings > Developer settings > Personal access tokens** on GitHub.
   - Click **Generate new token**, set scopes, and generate.

2. **Store the PAT Using Git Credential Manager**:

   Install Git Credential Manager:

   ```bash
   sudo apt install git-credential-manager-core
   ```

   Configure Git to use it:

   ```bash
   git config --global credential.helper manager-core
   ```

---

## Enhancing Your Shell with Zsh and

 Oh My Zsh

Zsh offers advanced features and customization options over the default Bash shell.

### Installing Zsh

```bash
sudo apt install zsh
```

Set Zsh as your default shell:

```bash
chsh -s $(which zsh)
```

### Installing Oh My Zsh

Oh My Zsh is a framework for managing Zsh configuration.

1. **Install Curl** (if not already installed):

   ```bash
   sudo apt install curl
   ```

2. **Install Oh My Zsh**:

   ```bash
   sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
   ```

### Adding Themes and Plugins

1. **Select a Theme**:

   - Edit `~/.zshrc` and set the `ZSH_THEME` variable. For example:

     ```bash
     ZSH_THEME="agnoster"
     ```

2. **Install Powerlevel10k Theme** (for an enhanced prompt):

   ```bash
   git clone --depth=1 https://github.com/romkatv/powerlevel10k.git \
   ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
   ```

   Set the theme in `~/.zshrc`:

   ```bash
   ZSH_THEME="powerlevel10k/powerlevel10k"
   ```

3. **Install Plugins**:

   - **zsh-autosuggestions**:

     ```bash
     git clone https://github.com/zsh-users/zsh-autosuggestions \
     ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
     ```

   - **zsh-syntax-highlighting**:

     ```bash
     git clone https://github.com/zsh-users/zsh-syntax-highlighting.git \
     ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
     ```

4. **Enable Plugins**:

   Edit `~/.zshrc`:

   ```bash
   plugins=(git zsh-autosuggestions zsh-syntax-highlighting)
   ```

5. **Apply Changes**:

   ```bash
   source ~/.zshrc
   ```

---

## Node.js and NVM

Node.js is essential for JavaScript development, and NVM allows you to manage multiple Node.js versions.

### Installing NVM

Install NVM (Node Version Manager):

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
```

Activate NVM:

```bash
export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
```

### Installing Node.js

Install the latest LTS (Long-Term Support) version:

```bash
nvm install --lts
```

### Managing Node Versions

List installed Node.js versions:

```bash
nvm ls
```

Switch between versions:

```bash
nvm use <version>
```

For example:

```bash
nvm use 14
```

### NPM Basics

Initialize a new Node.js project:

```bash
npm init -y
```

Install dependencies:

```bash
npm install package-name
```

Install a package globally:

```bash
npm install -g package-name
```

---

## Visual Studio Code

Visual Studio Code (VS Code) is a powerful, extensible code editor.

### Installing VS Code

Download and install VS Code from the [official website](https://code.visualstudio.com/).

### Configuring VS Code for WSL

1. **Install the Remote - WSL Extension**:

   - Open VS Code.
   - Go to the Extensions view (`Ctrl + Shift + X`).
   - Search for **Remote - WSL** and install it.

2. **Open a WSL Project in VS Code**:

   In your WSL terminal, navigate to your project directory and run:

   ```bash
   code .
   ```

### Essential Extensions

- **Live Server**: Launch a local development server with live reload.
- **Prettier - Code formatter**: Enforce a consistent style.
- **ESLint**: Integrate ESLint for JavaScript linting.
- **GitLens**: Enhance Git capabilities within VS Code.
- **Docker**: Add support for Docker files.
- **Bracket Pair Colorizer 2**: Color matching brackets.
- **Path Intellisense**: Autocomplete filenames.
- **VSCode-Icons**: Enrich the file explorer with icons.
- **Remote - SSH**: Connect to remote servers via SSH.

---

## Additional Code Editors and IDEs

While VS Code is popular, other editors and Integrated Development Environments (IDEs) may better suit your needs.

### Cursor IDE

**Cursor IDE** is an AI-powered code editor that enhances productivity.

1. **Download Cursor IDE**:

   Visit the [Cursor IDE website](https://www.cursor.so/) to download the installer.

2. **Install Cursor IDE**:

   Run the installer and follow the on-screen instructions.

3. **Features**:

   - AI-assisted code completion.
   - Intelligent error detection.
   - Code refactoring tools.

### Other IDEs

- **JetBrains IntelliJ IDEA**: Ideal for Java and Kotlin development.
- **PyCharm**: Specialized for Python projects.
- **WebStorm**: Excellent for JavaScript and TypeScript.
- **Visual Studio**: Comprehensive IDE for .NET development.

---

## Package Managers

Package managers simplify the installation and management of software.

### Chocolatey

Chocolatey is a Windows package manager.

#### Installing Chocolatey

1. **Open PowerShell as Administrator**.

2. **Run the Installation Command**:

   ```powershell
   Set-ExecutionPolicy Bypass -Scope Process -Force; `
   [System.Net.ServicePointManager]::SecurityProtocol = `
   [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; `
   iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
   ```

#### Using Chocolatey

- **Install a Package**:

  ```powershell
  choco install package-name -y
  ```

- **Upgrade All Packages**:

  ```powershell
  choco upgrade all -y
  ```

### Scoop

Scoop is another Windows package manager focused on simplicity.

#### Installing Scoop

1. **Ensure PowerShell Execution Policy is Unrestricted**:

   ```powershell
   Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
   ```

2. **Install Scoop**:

   ```powershell
   iwr -useb get.scoop.sh | iex
   ```

#### Using Scoop

- **Install a Package**:

  ```powershell
  scoop install package-name
  ```

- **Update Packages**:

  ```powershell
  scoop update *
  ```

---

## Additional Development Tools

Enhance your development environment with these tools.

### Docker Desktop

Docker allows you to containerize applications.

#### Installing Docker Desktop

1. **Download Docker Desktop** from the [official website](https://www.docker.com/products/docker-desktop).

2. **Install** and **restart your computer** if prompted.

#### Using Docker with WSL 2

Docker Desktop integrates with WSL 2 for improved performance.

- **Enable WSL 2 Backend**:

  In Docker Desktop settings, ensure **Use the WSL 2 based engine** is checked.

### Python and Pyenv

Manage multiple Python versions with Pyenv.

#### Installing Pyenv

1. **Install Dependencies**:

   ```bash
   sudo apt update && sudo apt install -y make build-essential libssl-dev \
   zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm \
   libncursesw5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev libffi-dev liblzma-dev
   ```

2. **Install Pyenv**:

   ```bash
   curl https://pyenv.run | bash
   ```

3. **Update Environment Variables**:

   Add the following to `~/.bashrc` or `~/.zshrc`:

   ```bash
   export PATH="$HOME/.pyenv/bin:$PATH"
   eval "$(pyenv init -)"
   eval "$(pyenv virtualenv-init -)"
   ```

4. **Restart Your Terminal**.

#### Managing Python Versions

- **List Available Versions**:

  ```bash
  pyenv install --list
  ```

- **Install a Version**:

  ```bash
  pyenv install 3.9.7
  ```

- **Set Global Version**:

  ```bash
  pyenv global 3.9.7
  ```

### Java Development Kit (JDK)

Set up Java development environment.

#### Installing JDK

Install OpenJDK:

```bash
sudo apt install openjdk-17-jdk
```

#### Verify Installation

```bash
java -version
```

---

## Browser Extensions

Enhance your web development workflow with these extensions.

- **React Developer Tools**: Inspect React component hierarchy.
- **Redux DevTools**: Debug Redux state changes.
- **Vue.js devtools**: Inspect Vue components.
- **Postman Interceptor**: Capture and send HTTP requests.
- **ColorZilla**: Advanced color picker.
- **WhatFont**: Identify fonts on web pages.
-

 **JSON Viewer**: Format JSON data.

---

## Productivity Tools

Boost your productivity with these applications.

- **PowerToys**: A set of utilities for power users.
- **Wox Launcher**: An efficient app launcher.
- **Notion**: Note-taking and project management.
- **Figma**: Collaborative design tool.
- **Slack**: Team communication platform.
- **Microsoft Teams**: Collaboration and communication.

---

## AI-Powered Tools

Leverage AI to enhance your development workflow.

### Wrap Terminal (macOS)

**Wrap** is an AI-powered terminal assistant for macOS users.

1. **Download Wrap**:

   Visit the [Wrap website](https://www.wrapwithus.com/) to download the application.

2. **Install Wrap**:

   Follow the installation instructions provided on the website.

3. **Features**:

   - Natural language command execution.
   - Intelligent command suggestions.
   - Error detection and correction.

### Other AI Tools

- **GitHub Copilot**: AI pair programmer that helps you write code faster.

  - **Installation**:

    Install the GitHub Copilot extension in VS Code.

  - **Features**:

    - Code suggestions and completions.
    - Supports multiple programming languages.

- **TabNine**: AI code completion for all major IDEs.

  - **Installation**:

    Install the TabNine plugin for your preferred IDE.

  - **Features**:

    - Whole-line and full-function code completions.
    - Learns from your codebase.

---

## Conclusion

Setting up a Windows development environment with the right tools and configurations can significantly enhance your productivity. By following this guide, you now have a robust setup ready for modern web development. Keep exploring and customizing your environment to suit your workflow. Don't forget to leverage AI-powered tools to further boost your efficiency.

---

## Additional Resources

- [Microsoft Docs - WSL](https://docs.microsoft.com/windows/wsl/)
- [Oh My Zsh Documentation](https://ohmyz.sh/)
- [Node Version Manager GitHub](https://github.com/nvm-sh/nvm)
- [Visual Studio Code Extensions Marketplace](https://marketplace.visualstudio.com/VSCode)
- [Docker Documentation](https://docs.docker.com/)
- [Pyenv GitHub](https://github.com/pyenv/pyenv)
- [Chocolatey Packages](https://community.chocolatey.org/packages)
- [Scoop Buckets](https://github.com/ScoopInstaller/Main)
- [Cursor IDE](https://www.cursor.so/)
- [Wrap Terminal](https://www.wrapwithus.com/)
- [GitHub Copilot](https://github.com/features/copilot)
- [TabNine](https://www.tabnine.com/)

---

*For more projects and resources, visit my [GitHub repository](https://github.com/a99divx).*
```

This markdown guide includes all of the steps you requested, enhanced and made more comprehensive. You can copy this directly into your repository's README.md file or any markdown file to create a professional, well-documented guide. Let me know if you need further adjustments!