# Content Management Guide

This guide explains how to manage content on your Hugo-based GitHub Pages site using two methods: a web-based UI and Notion integration.

## Method 1: Web-Based UI (Decap CMS)

Your site is configured with Decap CMS (formerly Netlify CMS) which provides a web-based interface for managing your content.

### Accessing the CMS

1. Navigate to `https://paarthmadan29.github.io/admin/` in your browser
2. You'll be redirected to GitHub for authentication
3. Authorize the application to access your repository
4. Once authenticated, you'll see the CMS dashboard

### Managing Posts

- **Creating Posts**: Click "New Post" in the "Posts" collection
- **Editing Posts**: Select a post from the list and make your changes
- **Deleting Posts**: In the post editor, click the settings icon and select "Delete"

### Post Fields

- **Title**: The title of your post
- **Publish Date**: When the post should be published
- **Description**: A brief description for SEO
- **Tags**: Comma-separated tags for categorization
- **Categories**: Comma-separated categories for organization
- **Draft**: Toggle to mark as draft (won't be published)
- **Featured Image**: Upload an image for the post
- **Body**: The main content of your post (supports Markdown)

## Method 2: Notion Integration

Your site includes automated synchronization with Notion. Posts created in a designated Notion database will be automatically converted to Hugo-compatible posts.

### Setting Up Notion Integration

1. Create a Notion database with the following properties:

   - **Name** (Title property): The title of the post
   - **Date** (Date property): Publication date
   - **Content** (Rich text property): The body content of the post
   - **Status** (Select property): Options should include "Published" (only published posts will be synced)

2. Obtain your Notion integration token and database ID
3. Add the following secrets to your GitHub repository:
   - `NOTION_TOKEN`: Your Notion integration token
   - `NOTION_DATABASE_ID`: The ID of your Notion database

### How It Works

- The GitHub Action runs hourly to sync new/updated posts from Notion
- Posts with a "Published" status in Notion will be created/updated in your Hugo site
- Changes made in Notion will overwrite the corresponding files in your repository

## Configuration Details

### Admin Configuration

The CMS configuration is located at `admin/config.yml` and specifies:

- GitHub as the backend for saving changes
- Posts are stored in the `posts/` directory
- Media files are stored in the `img/` directory

### GitHub Action

The Notion sync workflow is located at `.github/workflows/notion-sync.yml` and includes:

- Hourly scheduled runs
- Manual trigger capability
- Automatic Hugo site build and deployment

## Troubleshooting

### CMS Authentication Issues

- Make sure you have write access to the repository
- Clear browser cache if authentication fails repeatedly

### Notion Sync Issues

- Verify that your Notion integration is shared with the correct database
- Ensure the secret values are correctly set in GitHub
- Check the Actions tab in GitHub for workflow logs

## Security Notes

- Keep your Notion integration token secure
- Review all changes before approving pull requests
- Regularly audit who has access to your GitHub repository and Notion database
