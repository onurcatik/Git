# Deploying `mdBook` on GitHub Pages using GitHub Actions

This tutorial provides a step-by-step guide to deploying an `mdBook` to GitHub Pages using GitHub Actions. By the end of this guide, your book will be automatically built and published whenever you push changes to your repository.

## Prerequisites

1. **Install `mdBook`**: Ensure you have `mdBook` installed on your local machine.

   ```bash
   cargo install mdbook
   ```
2. **GitHub Repository**: Ensure you have a GitHub repository where you want to host your book.

## Folder Structure

Here is an example of the folder structure:

```
/your-repo
|-- .github/
|   |-- workflows/
|       |-- deploy.yml
|-- Django/
|   |-- book/
|   |-- src/
|   |-- book.toml
|-- .gitignore
|-- README.md
```

## Step-by-Step Guide

### 1. Create the Workflow File

1. Create a directory `.github/workflows` in the root of your repository if it doesn’t exist.

   ```bash
   mkdir -p .github/workflows
   ```
2. Inside this directory, create a file named `deploy.yml` with the following content:

   ```yaml
   name: Deploy mdBook to GitHub Pages

   on:
     push:
       branches:
         - main  # Adjust this if you use a different branch

   jobs:
     build-and-deploy:
       runs-on: ubuntu-latest

       steps:
         - name: Checkout code
           uses: actions/checkout@v2

         - name: Install Rust and mdBook
           run: |
             curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y
             source $HOME/.cargo/env
             cargo install mdbook

         - name: Build the book
           run: mdbook build Django  # 'Django' is your book directory

         - name: Deploy to GitHub Pages
           uses: peaceiris/actions-gh-pages@v3
           with:
             personal_token: ${{ secrets.PERSONAL_ACCESS_TOKEN }}
             publish_dir: ./Django/book  # Directory where mdBook outputs the built book
   ```

### 2. Configure `mdBook`

Ensure the `book.toml` file in the `Django` directory is properly configured. For example:

```toml
[book]
title = "Your Book Title"
author = "Your Name"
description = "A description of your book."

[build]
build-dir = "book"
```

### 3. Create a Personal Access Token (PAT)

1. **Go to GitHub**: Open your web browser and navigate to [GitHub](https://github.com).
2. **Access Developer Settings**:

   - Click on your profile picture in the top right corner.
   - Select `Settings` from the dropdown menu.
   - Scroll down to `Developer settings` on the left-hand side.
3. **Generate a New Token**:

   - Click on `Personal access tokens`.
   - Click on `Tokens (classic)` if not already there.
   - Click on `Generate new token`.

   Configure the token:

   - **Token name**: `GitHub Actions Deployment Token`
   - **Expiration**: Choose an appropriate duration (e.g., `90 days`).
   - **Select scopes**:

     - `repo` (Full control of private repositories)
     - `workflow` (Update GitHub Action workflows)
   - Click `Generate token`.
   - Copy the generated token.

### 4. Add the PAT as a Secret in Your Repository

1. **Navigate to Your Repository**:
   Open your repository on GitHub.
2. **Access Repository Settings**:

   - Click on `Settings`.
   - Scroll down to `Secrets and variables` > `Actions`.
   - Click `New repository secret`.
3. **Create the Secret**:

   - **Name**: `PERSONAL_ACCESS_TOKEN`
   - **Value**: Paste the PAT you copied earlier.
   - Click `Add secret`.

### 5. Push the Updated Workflow

Add, commit, and push your changes to the repository:

```bash
git add .github/workflows/deploy.yml
git commit -m "Update GitHub Actions workflow to use PAT"
git push origin main
```

### 6. Enable GitHub Pages

1. Go to your repository on GitHub.
2. Navigate to `Settings` > `Pages`.
3. Under `Source`, select the branch (`gh-pages`) and the folder (`/ (root)`) where your book will be deployed. Save the settings.

### 7. Verify Deployment

1. **Check GitHub Actions Logs**:

   - Go to your repository on GitHub.
   - Click on the `Actions` tab.
   - Select the most recent workflow run to see the detailed logs.
   - Look for any errors or issues in the logs.
2. **Access the GitHub Pages URL**:

   - The URL is typically in the format `https://<username>.github.io/<repository-name>`.

### Common Issues and Solutions

1. **Branch Protection Rules**:

   - Ensure there are no branch protection rules preventing the GitHub Actions bot from pushing to the `gh-pages` branch.
2. **CNAME Configuration**:

   - If you have a custom domain set up, ensure that the `CNAME` file is correctly configured in the `gh-pages` branch.
3. **Cache Issues**:

   - Try clearing your browser cache or accessing the site in incognito mode.

### Troubleshooting

If the deployment failed, here's a typical troubleshooting approach:

1. **Check for Errors in Logs**:

   - Identify and resolve any specific errors shown in the logs.
2. **Verify Token Permissions**:

   - Ensure the `PERSONAL_ACCESS_TOKEN` has the correct permissions (`repo` and `workflow` scopes).
3. **Re-run the Workflow**:

   - Manually re-run the workflow from the Actions tab after making any necessary corrections.

By following these steps, you should be able to deploy your `mdBook` to GitHub Pages successfully. If you encounter specific errors or need further assistance, feel free to seek help with the details.
