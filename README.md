
# Mac Setup Ansible Playbook

This Ansible playbook is designed to automate the setup of a developer-friendly environment on macOS. It installs a variety of essential tools, including programming languages, IDEs, utilities, and other development tools.

## Tools Installed

The following tools are installed and configured via Homebrew, Homebrew Cask, and other package managers:

- **Homebrew** (Package manager for macOS)
- **Development Tools:**
  - **Java**
  - **Go**
  - **Node.js (via NVM)**
  - **Rust (via rustup)**
  - **Python (via pyenv)**
  - **Scala (via SDKMAN)**
  - **SBT (via SDKMAN)**
- **Frontend Tools:**
  - **React Development Tools (via npm)**
  - **create-react-app, eslint, prettier, typescript (via npm)**
  - **Visual Studio Code**
  - **WebStorm**
  - **Obsidian**
  - **Warp**
- **Other Utilities:**
  - **Git**
  - **Spotify**
  - **iTerm**
  - **Oh My Zsh**
  - **Vim**
  - **Excalidraw Plugin for Obsidian**
  - **Git Plugin for Obsidian**
  - **Vimrc Support Plugin for Obsidian**

## Prerequisites

Before running this playbook, make sure you have the following:

- **macOS** (the playbook is designed for macOS environments)
- **Ansible** installed on your machine. You can install it using Homebrew:

    ```bash
    brew install ansible
    ```

- **Homebrew** installed on your system. If you don't have Homebrew installed, run:

    ```bash
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
    ```

## Usage

1. Clone the repository containing the Ansible playbook:

    ```bash
    git clone https://github.com/johnstamp/mac-setup.git
    cd mac-setup
    ```

2. Run the playbook with Ansible:

    ```bash
    ansible-playbook macbook-setup.yml --ask-become-pass
    ```

    - `--ask-become-pass` is used to prompt for the **sudo password** to install system-level dependencies.

3. The playbook will install and configure the following tools as listed above. It will also set up **Zsh**, **Oh My Zsh**, and various developer tools.

## Tags

This playbook uses **tags** to install specific tools individually:

- `react`: Install all React-related development tools.
- `obsidian`: Install Obsidian and related plugins.
- `warp`: Install Warp terminal.
- `git`: Install Git.
- `homebrew`: Install Homebrew if not already installed.

You can run specific tasks by using the `--tags` option:

```bash
ansible-playbook macbook-setup.yml --tags react

