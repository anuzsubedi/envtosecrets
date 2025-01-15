# EnvToSecrets

A tool to convert .env files to GitHub repository secrets easily.

## Description

EnvToSecrets is a command-line tool that simplifies the process of adding
multiple GitHub repository secrets at once by converting your local .env file
variables. This tool is particularly valuable when you need to add many secrets
to a repository, saving time and reducing the manual effort of adding each
secret individually through the GitHub interface.

## Prerequisites

1. [GitHub CLI](https://cli.github.com/) must be installed and authenticated
2. A GitHub repository where you want to add secrets

## Installation

### Installing GitHub CLI

```bash
# macOS
brew install gh

# Windows
winget install GitHub.cli

# Linux (Ubuntu/Debian)
curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null
sudo apt update
sudo apt install gh
```

### Authenticating GitHub CLI

1. Run the following command:

```bash
gh auth login
```

2. Follow the interactive prompts:
   - Select GitHub.com
   - Choose HTTPS protocol
   - Authenticate with your GitHub credentials

## Usage

1. Place your `.env` file in the same directory as the script
2. Edit `envtosecrets.sh` and replace `username/repository` with your GitHub
   repository details:
   ```bash
   # Example: change this line in the script
   GITHUB_REPO="yourusername/yourrepository"
   ```
3. Run the script:

```bash
./envtosecrets.sh
```

### .env File Format

Your .env file should follow the standard format:

```
API_KEY=your_api_key
DATABASE_URL=your_database_url
SECRET_TOKEN=your_secret_token
```
