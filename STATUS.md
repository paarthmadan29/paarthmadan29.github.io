# Site Status

✅ **Current Setup**: Notion-only content management
✅ **Deployment**: GitHub Pages with Hugo
✅ **Sync Frequency**: Every 2 hours
✅ **Manual Trigger**: Available through GitHub Actions

## How to Manage Content

1. **Create/Edit Posts in Notion**

   - Use your configured Notion database
   - Set status to "Published" for posts to appear on site
   - Posts sync automatically every 2 hours

2. **Manual Sync**

   - Go to GitHub → Actions → Notion Content Sync
   - Click "Run workflow" to trigger immediate sync
   - Enable debug mode for detailed logs

3. **View Your Site**
   - Visit: https://paarthmadan29.github.io
   - Posts appear automatically after syncing

## Required GitHub Secrets

Make sure these are configured in your repository settings:

- `NOTION_TOKEN`: Your Notion integration token
- `NOTION_DATABASE_ID`: Your Notion database ID

## Need Help?

See [NOTION_SETUP.md](./NOTION_SETUP.md) for detailed setup instructions.
