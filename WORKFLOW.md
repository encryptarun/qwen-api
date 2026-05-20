# GitHub Actions Workflow: Auto-Refresh Access Token

This repository includes a GitHub Actions workflow that automatically refreshes the access token and updates both the token and expiry date in the README every 5 days.

## 🔄 How It Works

The workflow (`/.github/workflows/refresh-token.yml`) performs the following steps:

1. **Token Extraction**: Extracts the current access token from the README.md file
2. **Token Refresh**: Calls the Qwen API refresh endpoint to get a new access token and expiry date
3. **README Update**: Updates both the access token and expiry date in the README
4. **Git Commit**: Commits and pushes the changes back to the repository

## ⏰ Schedule

- **Automatic**: Runs every 5 days at 00:00 UTC
- **Manual**: Can be triggered manually via the "Actions" tab in GitHub

## 🚀 Manual Trigger

To manually trigger the workflow:

1. Go to the "Actions" tab in your GitHub repository
2. Select "Refresh Access Token and Update README" workflow
3. Click "Run workflow" button
4. Click "Run workflow" to confirm

## 📋 Workflow Features

- ✅ **Token Refresh**: Automatically refreshes access tokens to prevent expiry
- ✅ **Dual Updates**: Updates both access token and expiry date in README
- ✅ **Direct Updates**: Overwrites README directly without creating backups
- ✅ **Error Handling**: Comprehensive error checking for API calls and token extraction
- ✅ **Change Detection**: Only commits when changes are actually needed
- ✅ **Detailed Logging**: Provides clear feedback about what's happening

## 🔧 Configuration

The workflow is configured in `.github/workflows/refresh-token.yml`. Key settings:

- **Schedule**: `"0 0 */5 * *"` (every 5 days at midnight UTC)
- **API Endpoint**: `https://qwen.aikit.club/v1/refresh`
- **Target File**: `README.md`
- **Git User**: `github-actions[bot]`

## 📝 Notes

- The workflow automatically detects the token format in the README
- Both access token and expiry date are refreshed and updated directly
- It preserves the exact format of the expiry date returned by the API
- Changes are only made if either the token or expiry date differs
- Direct overwrite approach - no backup files created
- All operations include comprehensive error handling and logging
- The refresh endpoint provides fresh tokens to prevent service interruption
