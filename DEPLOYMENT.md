# I have done deployment using nxtwave platform
# The other way to deploy is as follows

# 1. Prepare Your Repository
Ensure all your project files (HTML, CSS, JavaScript, etc.) are committed and pushed to a GitHub repository.
# 2. Set Up GitHub Pages
GitHub Pages can serve static websites directly from your repository.

# Deployment Steps
Go to your repository on GitHub.
Navigate to Settings > Pages.
In the Source section:
Choose the branch (e.g., main) from which to deploy.
Set the folder as /root if all files are in the root directory.
Click Save.
GitHub will generate a deployment URL (e.g., https://<username>.github.io/<repository>).
# 3. Deployment Configuration File
If your project requires additional settings (like frameworks or builds), you can use the following GitHub Actions workflow file for automated deployment. However, for a simple static site, this file is optional.

Create .github/workflows/deploy.yml
Add the following file to your repository:

yaml
Copy code
name: Deploy to GitHub Pages

on:
  push:
    branches:
      - main  # Deploy whenever the main branch is updated

jobs:
  deploy:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout repository
      uses: actions/checkout@v3

    - name: Set up GitHub Pages
      uses: actions/configure-pages@v3

    - name: Deploy to GitHub Pages
      uses: actions/upload-pages-artifact@v1

    - name: Publish
      uses: actions/deploy-pages@v1
# 4. Testing Your Deployment
After pushing changes, wait a few minutes for GitHub Pages to process the deployment.
Visit the URL provided in the GitHub Pages settings to verify your site is live.

### Public URL
Your application is now live and can be accessed at https://pravalitourism.ccbp.tech/
