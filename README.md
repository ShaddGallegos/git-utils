# GitHub Repository Management Utilities

A comprehensive command-line tool for managing GitHub repositories with features for branch protection, pull request management, and repository administration.

## Overview

`gh-utils` provides a streamlined interface for common GitHub repository management tasks, helping developers manage their repositories more efficiently without needing to navigate through the GitHub web interface for routine operations.

## Features

- **Branch Protection Management**
  - Apply custom protection rules to branches
  - Remove protection from branches
  - Visualize branch relationships and protection status

- **Pull Request Workflows**
  - List, review, and merge pull requests
  - Approve pull requests with comments
  - View PR details including commits, files changed, and comments

- **Repository Creation**
  - Create new GitHub repositories from local directories
  - Initialize repositories with README files
  - Configure local Git repository with remote connection

- **Authentication**
  - Secure token-based authentication
  - Support for both public GitHub and GitHub Enterprise
  - Automatic credential management

## Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/git-utils.git
cd git-utils

# Make the script executable
chmod +x gh-utils

# Optional: Add to your PATH for easier access
cp gh-utils ~/.local/bin/
```

## Requirements

The script will automatically check for and install required dependencies, including:

- PyGithub (≥1.55)
- colorama (≥0.4.4)
- keyring (≥23.0)

Optional but recommended dependencies for enhanced UI:

- rich
- questionary

## Usage

### Basic Usage

```bash
./gh-utils
```

This launches the interactive menu where you can select various operations to perform.

### Command-line Options

The tool also supports direct command-line parameters for quick operations:

```bash
# Merge a specific pull request by number
./gh-utils --merge 123

# Create a new repository from the current directory
./gh-utils --create my-new-repo

# Apply branch protection to a specific branch
./gh-utils --protect main

# Show repository statistics
./gh-utils --stats
```

## Advanced Python Environment Setup

The script can automatically use the latest available Python version on your system and create an isolated environment for its dependencies:

```bash
# Run with automatic Python version detection
python3 gh-utils

# Use a specific Python installation 
/path/to/python3.12 gh-utils

# Skip virtual environment creation
python3 gh-utils --no-venv

# Force use of system Python without checks
python3 gh-utils --use-system-python
```

### Install Python 3.12

```bash
sudo dnf install python3.12 python3.12-devel
python3.12 gh-utils
```

## Common Workflows

### Protecting a Branch

1. Run `gh-utils`
2. Select "Apply Branch Protection" (option 2)
3. Enter your repository details when prompted
4. Select the branch you want to protect
5. Configure protection settings:
   - Pull request review requirements
   - Required status checks
   - Admin enforcement options

### Managing Pull Requests

1. Run `gh-utils`
2. Select "Review & Merge Pull Requests" (option 5)
3. Enter your repository details when prompted
4. Select a pull request from the list
5. Review details including commits, files, and comments
6. Choose to approve, comment on, or merge the pull request

### Creating a GitHub Repository

1. Run `gh-utils`
2. Select "Create Repository from Local Directory" (option 6)
3. Enter the path to your local directory
4. Provide GitHub credentials and repository details
5. The tool will initialize Git, create the remote repository, and push your code

## Authentication

The tool requires a GitHub Personal Access Token with appropriate permissions:

- `repo` scope for private repositories
- `public_repo` scope for public repositories
- `admin:org` if working with organization repositories

## Troubleshooting

If you encounter issues:

1. Check the log file at `~/.gh-utils/gh-utils.log` for errors
2. Ensure your GitHub token has the necessary permissions
3. For network-related issues, check your connection to GitHub

## License

MIT License

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.