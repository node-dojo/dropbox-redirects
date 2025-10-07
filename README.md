# Dropbox Redirects

This repository hosts redirect pages that open Dropbox folders using deep links.

## How it works

1. The `index.html` file contains JavaScript that:
   - Extracts the project path from URL parameters
   - Converts it to a Dropbox deep link (`dbx://dropbox/home/path`)
   - Attempts to open the Dropbox desktop app
   - Falls back to Dropbox web interface if the app isn't available

## Setup Instructions

### 1. Create GitHub Repository
1. Go to [GitHub](https://github.com) and create a new repository
2. Name it `dropbox-redirects`
3. Make it public (required for free GitHub Pages)
4. Don't initialize with README (we'll add our own)

### 2. Upload Files
1. Upload the `index.html` file to the repository
2. Upload this `README.md` file
3. Commit the changes

### 3. Enable GitHub Pages
1. Go to your repository settings
2. Scroll down to "Pages" section
3. Under "Source", select "Deploy from a branch"
4. Choose "main" branch and "/ (root)" folder
5. Click "Save"

### 4. Get Your URL
Your GitHub Pages URL will be: `https://YOUR_USERNAME.github.io/dropbox-redirects`

### 5. Update Monitoring System
Update the redirect URL in `monitor_project.py`:
```python
redirect_url = f"https://YOUR_USERNAME.github.io/dropbox-redirects/?path={encoded_path}"
```

## Usage

Access redirects using: `https://YOUR_USERNAME.github.io/dropbox-redirects/?path=encoded_path`

Where `encoded_path` is the URL-encoded full local path to the Dropbox folder.

## Testing

Test your redirect by visiting:
`https://YOUR_USERNAME.github.io/dropbox-redirects/?path=/Users/joebowers/Library/CloudStorage/Dropbox/Caveman%20Creative/THE%20WELL_Digital%20Assets/The%20Well%20Code/Project%20Tracking`

This should open the Project Tracking folder in Dropbox.
