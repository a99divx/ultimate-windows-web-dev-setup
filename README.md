![Windows 11 Web Development Environment](/assets/windows11-webdev-environment.png)

# The Ultimate Guide to Setting Up a Windows 11 Web Development Environment 🚀

⌚ Last Update: 16:47:29 UTC - Friday, 20 September 2024

Setting up a powerful and efficient web development environment on Windows 11 doesn't have to be overwhelming. This guide will walk you through the process of installing essential tools, configuring your system for optimal performance, and introducing advanced tips and tricks to make your setup the best it can be. We'll cover everything from basic installations to advanced configurations, ensuring you're equipped with the knowledge to create a top-tier development environment.

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

---

## Table of Contents 📚

1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
3. [Setting Up Windows Subsystem for Linux (WSL 2)](#setting-up-windows-subsystem-for-linux-wsl-2)
4. [Configuring Windows Terminal](#configuring-windows-terminal)
5. [Setting Up Git and GitHub](#setting-up-git-and-github)
6. [Enhancing Your Shell with Zsh and Oh My Zsh](#enhancing-your-shell-with-zsh-and-oh-my-zsh)
7. [Installing Node.js and pnpm](#installing-nodejs-and-pnpm)
8. [Visual Studio Code Setup](#visual-studio-code-setup)
9. [Exploring Additional Code Editors and IDEs](#exploring-additional-code-editors-and-ides)
10. [Using Package Managers: Chocolatey and Scoop](#using-package-managers-chocolatey-and-scoop)
11. [Additional Development Tools](#additional-development-tools)
12. [Browser Extensions for Developers](#browser-extensions-for-developers)
13. [Productivity Tools](#productivity-tools)
14. [Leveraging AI-Powered Tools](#leveraging-ai-powered-tools)
15. [Advanced Tips and Tricks](#advanced-tips-and-tricks)
16. [Conclusion](#conclusion)
17. [Additional Resources](#additional-resources)

---

## Introduction 🌐

In today's fast-paced development environment, having a fully optimized setup is crucial for productivity and efficiency. This guide aims to help you configure the **best web development environment on Windows 11**, leveraging powerful tools like **Windows Subsystem for Linux (WSL 2)**, modern terminals, and AI-driven coding assistants. We'll delve into advanced configurations, explore a plethora of tools, and provide tips and tricks to enhance your workflow.

---

## Prerequisites 📝

Before we begin, ensure you have the following:

- **Operating System**: Windows 10 version 2004 or higher, or Windows 11
- **User Account**: Administrative privileges
- **Internet Access**: For downloading tools and updates
- **GitHub Account**: Sign up [here](https://github.com/) if you don't have one

---

## Setting Up Windows Subsystem for Linux (WSL 2) 🐧

WSL allows you to run a Linux environment directly on Windows, providing a seamless integration between Windows and Linux development environments.

### Installing WSL 2

1. **Enable WSL and Install a Linux Distribution**:

   Open **PowerShell** as **Administrator** and run:

   ```powershell
   wsl --install
   ```

   This command will:

   - Enable the required optional components.
   - Download and install the latest Linux kernel.
   - Set WSL 2 as the default.
   - Install Ubuntu as the default Linux distribution.

2. **Restart Your Computer**:

   Restart to complete the WSL installation.

### Initial Configuration of WSL

1. **Launch Ubuntu**:

   Open Ubuntu from the Start menu. It will take a few moments to set up.

2. **Create a UNIX Username and Password**:

   You'll be prompted to create a UNIX username and password. This is separate from your Windows credentials.

### Updating and Upgrading Linux

Keep your Linux environment up to date:

```bash
sudo apt update && sudo apt upgrade -y
```

### Accessing Linux Files from Windows

Access your Linux files directly from Windows:

1. **Using File Explorer**:

   Navigate to:

   ```
   \\wsl$
   ```

   This will show all your installed WSL distributions.

2. **Mapping a Network Drive**:

   - Right-click on the `Ubuntu` folder.
   - Select **Map network drive...**.
   - Choose a drive letter (e.g., `Z:`).
   - Check **Reconnect at sign-in**.
   - Click **Finish**.

   Your Linux home directory is now accessible from Windows as a network drive.

### Restarting WSL

If you encounter issues:

```powershell
wsl --shutdown
```

Then relaunch your Linux distribution.

### Windows-Specific Considerations

- **File System Performance**: For best performance, keep your project files within the Linux file system (`/home/username/`).
- **Line Endings**: Use a `.gitattributes` file to ensure consistent line endings across Windows and Linux.
- **Path Differences**: Be mindful of path formats when working across systems.
- **Permissions**: Some operations may require elevated privileges in WSL.

### Running GUI Applications with WSLg

With WSLg, you can run Linux GUI applications directly on Windows:

- **Ensure WSL is Updated**:

  ```powershell
  wsl --update
  ```

- **Launch GUI Applications**:

  ```bash
  xclock  # Example GUI application
  ```

---

## Configuring Windows Terminal 🖥️

Windows Terminal is a modern, feature-rich terminal application that supports multiple tabs, split panes, and extensive customization.

### Installing Windows Terminal

Download from the [Microsoft Store](https://aka.ms/terminal) or via PowerShell:

```powershell
winget install --id=Microsoft.WindowsTerminal -e
```

### Customizing Windows Terminal

1. **Set Default Profile**:

   - Open Windows Terminal.
   - Click the **down arrow** next to the **new tab** button and select **Settings**.
   - Under **Startup**, set **Default profile** to **Ubuntu**.

2. **Set Starting Directory**:

   - In **Profiles**, select **Ubuntu**.
   - Under **Advanced**, set **Starting directory** to:

     ```
     \\wsl$\Ubuntu\home\your_username
     ```

3. **Customize Appearance**:

   - Explore the **Appearance** tab to change the theme, font, and background.
   - Install a Powerline font like [MesloLGS NF](https://github.com/romkatv/powerlevel10k#manual-font-installation) for better prompt symbols.

4. **Install Themes**:

   - Visit [Windows Terminal Themes](https://windowsterminalthemes.dev/) to find and install new themes.
   - You can import themes by editing the `settings.json` file.

5. **Configure Keyboard Shortcuts and Actions**:

   - Customize keybindings to suit your workflow.
   - Set up actions like split panes, duplicate tabs, etc.

---

## Setting Up Git and GitHub 🧑‍💻

Git is essential for version control, and GitHub hosts your repositories.

### Installing Git

Git is typically pre-installed in your WSL distribution. If not, install it:

```bash
sudo apt install git
```

### Configuring Git

Set up your global Git configuration:

```bash
git config --global user.name "Your Name"
git config --global user.email "youremail@example.com"
```

Set up default branch name to `main`:

```bash
git config --global init.defaultBranch main
```

Verify your settings:

```bash
git config --list
```

### Generating SSH Keys for GitHub

1. **Generate a New SSH Key**:

   ```bash
   ssh-keygen -t ed25519 -C "youremail@example.com"
   ```

   Press `Enter` to accept the default file location. Set a passphrase if desired.

2. **Start the SSH Agent**:

   ```bash
   eval "$(ssh-agent -s)"
   ```

3. **Add Your SSH Key**:

   ```bash
   ssh-add ~/.ssh/id_ed25519
   ```

4. **Add the Key to Your GitHub Account**:

   - Copy your public key:

     ```bash
     cat ~/.ssh/id_ed25519.pub
     ```

   - Log in to GitHub.
   - Go to **Settings > SSH and GPG keys**.
   - Click **New SSH key**, provide a title, and paste your key.

### Using Personal Access Tokens (Optional)

If you prefer HTTPS over SSH:

1. **Generate a Personal Access Token (PAT)**:

   - On GitHub, go to **Settings > Developer settings > Personal access tokens**.
   - Click **Generate new token**, select scopes, and generate.

2. **Configure Git Credential Manager**:

   ```bash
   git config --global credential.helper store
   ```

   The next time you authenticate with GitHub, enter your PAT as the password.

---

## Enhancing Your Shell with Zsh and Oh My Zsh 🐚

Zsh is an advanced shell that offers powerful features and customization.

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

1. **Install Curl (if not installed)**:

   ```bash
   sudo apt install curl
   ```

2. **Install Oh My Zsh**:

   ```bash
   sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
   ```

### Adding Themes and Plugins

1. **Install Powerlevel10k Theme**:

   ```bash
   git clone --depth=1 https://github.com/romkatv/powerlevel10k.git \
     ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
   ```

   Set the theme in `~/.zshrc`:

   ```bash
   ZSH_THEME="powerlevel10k/powerlevel10k"
   ```

2. **Install Recommended Fonts**:

   Download and install the [MesloLGS NF](https://github.com/romkatv/powerlevel10k#manual-font-installation) font.

   - **Windows Terminal**: Set the font face to "MesloLGS NF" in settings.

3. **Install Useful Plugins**:

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

   - **zsh-completions**:

     ```bash
     git clone https://github.com/zsh-users/zsh-completions \
       ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-completions
     ```

4. **Enable Plugins**:

   Edit `~/.zshrc`:

   ```bash
   plugins=(git zsh-autosuggestions zsh-syntax-highlighting zsh-completions)
   ```

5. **Apply Changes**:

   ```bash
   source ~/.zshrc
   ```

6. **Configure Powerlevel10k**:

   Run the configuration wizard:

   ```bash
   p10k configure
   ```

   Follow the prompts to customize your prompt.

7. **Advanced Aliases and Functions**:

   Add custom aliases and functions to your `~/.zshrc` for increased productivity.

---

## Installing Node.js and pnpm 🟢

Node.js is essential for JavaScript development, and `pnpm` is a fast, disk space-efficient package manager.

### Installing NVM (Node Version Manager)

Install NVM to manage multiple Node.js versions:

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.5/install.sh | bash
```

Activate NVM:

```bash
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
```

Add these lines to your `~/.zshrc` or `~/.bashrc` to load NVM automatically.

### Installing Node.js via NVM

Install the latest LTS version:

```bash
nvm install --lts
```

Set the default Node.js version:

```bash
nvm alias default node
```

### Installing pnpm

Install pnpm globally:

```bash
npm install -g pnpm
```

Alternatively, use the installation script:

```bash
curl -fsSL https://get.pnpm.io/install.sh | sh -
```

Ensure pnpm is in your PATH by adding to `~/.zshrc` or `~/.bashrc`:

```bash
export PATH="$HOME/.local/share/pnpm:$PATH"
```

Reload your shell configuration:

```bash
source ~/.zshrc
```

### Using pnpm

- **Initialize a New Project**:

  ```bash
  pnpm init
  ```

- **Install Dependencies**:

  ```bash
  pnpm install package-name
  ```

- **Install a Package Globally**:

  ```bash
  pnpm add -g package-name
  ```

- **Update Packages**:

  ```bash
  pnpm update
  ```

- **Clean Up Dependencies**:

  ```bash
  pnpm prune
  ```

---

## Visual Studio Code Setup 📝

Visual Studio Code is a versatile code editor with extensive extension support.

### Installing Visual Studio Code

Download from the [official website](https://code.visualstudio.com/).

### Configuring VS Code for WSL

1. **Install the Remote - WSL Extension**:

   - Open VS Code.
   - Go to the Extensions view (`Ctrl+Shift+X`).
   - Search for **Remote - WSL** and install it.

2. **Open a WSL Project in VS Code**:

   In your WSL terminal, navigate to your project directory and run:

   ```bash
   code .
   ```

### Essential Extensions 🔌

- **Live Server**: Launch a local development server with live reload.
- **Prettier**: Code formatter for consistent style.
- **ESLint**: Integrate ESLint for JavaScript linting.
- **GitLens**: Enhance Git capabilities within VS Code.
- **Docker**: Support for Docker files.
- **Bracket Pair Colorizer 2**: Color matching brackets.
- **Path Intellisense**: Autocomplete filenames.
- **vscode-icons**: Enrich the file explorer with icons.
- **Remote - SSH**: Connect to remote servers via SSH.
- **Thunder Client**: Lightweight REST API client.
- **Settings Sync**: Synchronize settings across devices.

### Settings Sync

Leverage VS Code's **Settings Sync** feature to synchronize your settings, extensions, and keybindings across devices.

### Advanced Configuration

- **Workspace Settings**: Customize settings per project.
- **Snippets**: Create code snippets for frequently used code blocks.
- **Keybindings**: Customize shortcuts to enhance productivity.
- **User Settings**: Tailor the editor to your preferences.

---

## Exploring Additional Code Editors and IDEs 🖊️

While VS Code is popular, other editors and IDEs may better suit your needs.

### Cursor IDE

Cursor IDE is an AI-powered code editor that enhances productivity.

1. **Download Cursor IDE**:

   Visit the [Cursor IDE website](https://www.cursor.so/) to download.

2. **Features**:

   - AI-assisted code completion.
   - Intelligent error detection.
   - Code refactoring and generation tools.
   - Integration with popular version control systems.
   - Customizable interface and themes.

### Other IDEs

- **JetBrains IntelliJ IDEA**: Ideal for Java and Kotlin development.
- **PyCharm**: Specialized for Python projects.
- **WebStorm**: Excellent for JavaScript and TypeScript.
- **Visual Studio**: Comprehensive IDE for .NET development.
- **Sublime Text**: Lightweight and fast text editor.
- **Atom**: Hackable text editor for the 21st century.

---

## Using Package Managers: Chocolatey and Scoop 📦

Package managers simplify the installation and management of software on Windows.

### Chocolatey

Chocolatey is a powerful package manager for Windows.

#### Installing Chocolatey

1. **Open PowerShell as Administrator**.

2. **Run the Installation Command**:

   ```powershell
   Set-ExecutionPolicy Bypass -Scope Process -Force;
   [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072;
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

- **Search for Packages**:

  ```powershell
  choco search package-name
  ```

### Scoop

Scoop focuses on simplicity and minimizes the need for administrative privileges.

#### Installing Scoop

1. **Ensure PowerShell Execution Policy**:

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

- **Add Buckets for More Packages**:

  ```powershell
  scoop bucket add extras
  ```

---

## Additional Development Tools 🛠️

### Docker Desktop 🐳

Docker enables containerization, making it easier to deploy and manage applications.

#### Installing Docker Desktop

1. **Download Docker Desktop** from the [official website](https://www.docker.com/products/docker-desktop).

2. **Install and Restart** your computer if prompted.

#### Configuring Docker with WSL 2

- **Enable WSL 2 Backend**:

  In Docker Desktop settings, ensure **Use the WSL 2 based engine** is checked.

- **Resource Management**:

  Configure CPU and memory allocation in Docker Desktop settings under **Resources**.

- **Integrate with WSL Distributions**:

  Under **Resources > WSL Integration**, enable Docker integration with your WSL distributions.

### Database Tools

- **MySQL Workbench**: Visual tool for MySQL databases.
- **pgAdmin**: Feature-rich PostgreSQL administration tool.
- **MongoDB Compass**: GUI for MongoDB.

### Virtualization Tools

- **VirtualBox**: Open-source virtualization software.
- **Vagrant**: Manage and configure virtual machine environments.

### API Testing Tools

- **Postman**: Powerful API testing tool.
- **Insomnia**: REST API client with GraphQL support.

### Version Control Systems

- **GitKraken**: Cross-platform Git client.
- **SourceTree**: Visual Git and Mercurial client.

---

## Browser Extensions for Developers 🌐

Enhance your web development workflow with these browser extensions.

- **React Developer Tools**: Inspect React component hierarchy.
- **Redux DevTools**: Debug Redux state changes.
- **Vue.js devtools**: Inspect Vue components.
- **Angular DevTools**: Debug Angular applications.
- **Svelte DevTools**: Debug Svelte applications.
- **Postman Interceptor**: Capture and send HTTP requests.
- **JSON Viewer**: Format JSON data.
- **ColorZilla**: Advanced color picker.
- **WhatFont**: Identify fonts on web pages.
- **Wappalyzer**: Identify technologies used on websites.
- **Lighthouse**: Audit web apps for performance and accessibility.

---

## Productivity Tools ⚙️

Boost your productivity with these applications.

- **Microsoft PowerToys**: Utilities like FancyZones, PowerRename, and more.
- **Windows Terminal**: Advanced terminal application.
- **AutoHotkey**: Automate repetitive tasks.
- **WSLtty**: Alternative terminal for WSL.
- **Notion**: Note-taking and project management.
- **Obsidian**: Powerful knowledge base on top of a local folder of plain text Markdown files.
- **Figma**: Collaborative design tool.
- **Slack**: Team communication platform.
- **Microsoft Teams**: Collaboration and communication.
- **Todoist**: Task management.
- **RescueTime**: Personal analytics service.

---

## Leveraging AI-Powered Tools 🤖

Enhance your coding efficiency with AI assistants.

### GitHub Copilot

An AI pair programmer that helps you write code faster.

- **Installation**:

  Install the GitHub Copilot extension in VS Code.

- **Features**:

  - Context-aware code suggestions.
  - Supports multiple programming languages.
  - Can generate code snippets, functions, and even complex algorithms.

### Tabnine

AI code completion for all major IDEs.

- **Installation**:

  Install the Tabnine plugin for your preferred IDE.

- **Features**:

  - Whole-line and full-function code completions.
  - Learns from your codebase for personalized suggestions.

### Codeium

Free AI-powered code acceleration toolkit.

- **Installation**:

  Install the Codeium extension in your code editor.

- **Features**:

  - Code completion and suggestions.
  - Supports multiple languages and editors.

### Amazon CodeWhisperer

An AI coding companion that generates code suggestions.

- **Installation**:

  Install the AWS Toolkit extension in VS Code.

- **Features**:

  - Code recommendations based on your comments and existing code.
  - Supports multiple programming languages.
  - Integration with AWS services.

---

## Advanced Tips and Tricks 🧙‍♂️

Elevate your development environment with these advanced configurations.

### Terminal Multiplexers

- **Tmux**: Terminal multiplexer to manage multiple terminal sessions.

  ```bash
  sudo apt install tmux
  ```

- **Byobu**: Enhanced profile and configuration utilities for Tmux.

  ```bash
  sudo apt install byobu
  ```

### Dotfiles Management

- Use a Git repository to manage your dotfiles (`.bashrc`, `.zshrc`, etc.).
- Automate environment setup across multiple machines.

### SSH Configurations

- **SSH Config File**: Simplify SSH connections by editing `~/.ssh/config`.

  ```bash
  Host myserver
      HostName example.com
      User username
      IdentityFile ~/.ssh/id_rsa
  ```

### Firewall and Security

- **UFW (Uncomplicated Firewall)**:

  ```bash
  sudo apt install ufw
  sudo ufw enable
  ```

### Performance Monitoring Tools

- **htop**: Interactive process viewer.

  ```bash
  sudo apt install htop
  ```

- **glances**: System monitoring tool.

  ```bash
  sudo apt install glances
  ```

### Network Tools

- **net-tools**: Networking utilities.

  ```bash
  sudo apt install net-tools
  ```

- **nmap**: Network exploration tool.

  ```bash
  sudo apt install nmap
  ```

### Alias and Functions

- Create custom aliases in `~/.zshrc` or `~/.bashrc`:

  ```bash
  alias gs='git status'
  alias gp='git pull'
  alias gc='git commit -m'
  ```

### Custom Scripts

- Automate repetitive tasks with shell scripts.
- Add your scripts to a `~/bin` directory and include it in your PATH.

### Virtual Environments

- **Python**:

  ```bash
  python -m venv venv
  source venv/bin/activate
  ```

- **Node.js**:

  Use `nvm` to manage versions and isolate environments.

### Managing Background Services

- Use **pm2** for Node.js applications:

  ```bash
  npm install -g pm2
  pm2 start app.js
  ```

### Configuring Environment Variables

- Store environment variables in `.env` files.
- Use packages like **dotenv** to manage them in your applications.

---

## Conclusion 🎯

By incorporating these tools and configurations, you're setting up a professional-grade web development environment on Windows 11. This guide has provided a comprehensive walkthrough, from installing WSL and configuring your terminal to leveraging AI-powered coding assistants and advanced tips.

Embrace these tools to enhance your productivity, streamline your workflow, and tackle complex development projects with confidence.

Happy coding! 💻

---

## Additional Resources 📚

- **Windows Subsystem for Linux Documentation**: [WSL Docs](https://docs.microsoft.com/en-us/windows/wsl/)
- **Windows Terminal Documentation**: [Terminal Docs](https://docs.microsoft.com/en-us/windows/terminal/)
- **Git Documentation**: [Git Docs](https://git-scm.com/doc)
- **GitHub Documentation**: [GitHub Docs](https://docs.github.com/)
- **Zsh Documentation**: [Zsh Docs](https://zsh.sourceforge.io/Doc/)
- **Oh My Zsh Documentation**: [Oh My Zsh Docs](https://ohmyz.sh/)
- **Node.js Documentation**: [Node.js Docs](https://nodejs.org/en/docs/)
- **NVM Documentation**: [NVM Docs](https://github.com/nvm-sh/nvm#readme)
- **pnpm Documentation**: [pnpm Docs](https://pnpm.io/)
- **Visual Studio Code Documentation**: [VS Code Docs](https://code.visualstudio.com/docs)
- **Chocolatey Documentation**: [Chocolatey Docs](https://docs.chocolatey.org/)
- **Scoop Documentation**: [Scoop Docs](https://scoop.sh/)
- **Docker Documentation**: [Docker Docs](https://docs.docker.com/)
- **Python Documentation**: [Python Docs](https://docs.python.org/)
- **Pyenv Documentation**: [Pyenv Docs](https://github.com/pyenv/pyenv#readme)
- **Java Documentation**: [Java Docs](https://docs.oracle.com/en/java/)
- **PowerToys Documentation**: [PowerToys Docs](https://docs.microsoft.com/en-us/windows/powertoys/)
- **Notion Documentation**: [Notion Help](https://www.notion.so/help)
- **Figma Documentation**: [Figma Help](https://help.figma.com/)
- **Slack Documentation**: [Slack Help](https://slack.com/help)
- **Microsoft Teams Documentation**: [Teams Docs](https://docs.microsoft.com/en-us/microsoftteams/)
- **GitHub Copilot Documentation**: [Copilot Docs](https://docs.github.com/en/copilot)
- **Tabnine Documentation**: [Tabnine Docs](https://www.tabnine.com/docs)
- **Codeium Documentation**: [Codeium Docs](https://docs.codeium.com/)
- **Amazon CodeWhisperer Documentation**: [CodeWhisperer Docs](https://aws.amazon.com/codewhisperer/)

---

Feel free to reach out if you have any questions or need further assistance.

Happy coding! 😊