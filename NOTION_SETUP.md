# Setting up Notion Database for Hugo Integration

This guide will help you set up a Notion database that works with the Hugo integration.

## Creating the Database

1. Create a new Notion database page
2. Set up the following properties:

### Required Properties

- **Name** (Type: Title) - This will become the post title
- **Date** (Type: Date) - Publication date for the post
- **Content** (Type: Rich text) - Main content of the post
- **Status** (Type: Select) - Options: "Draft", "Published"

### Optional Properties (but recommended)

- **Tags** (Type: Multi-select) - For post tagging
- **Category** (Type: Select) - For post categorization
- **Author** (Type: People) - To track authorship
- **Featured Image** (Type: Files & media) - For featured images

## Property Configuration Details

### Name (Title)

- Type: Title
- This is the only required field in Notion
- Will become the `title` in Hugo front matter

### Date

- Type: Date
- Will become the `date` in Hugo front matter

### Content

- Type: Rich text
- This is where your post content goes
- Will become the main content body in Hugo posts

### Status

- Type: Select
- Options: "Draft", "Published" (you can add more like "Review", "Scheduled")
- Only posts with "Published" status will be synced to Hugo

### Tags

- Type: Multi-select
- Add various tags you might want to use
- Will become the `tags` array in Hugo front matter

### Category

- Type: Select
- Add categories you might want to use
- Will become the `categories` array in Hugo front matter

## Sample Database Entry

Here's how a typical entry should look:

| Name               | Date       | Status    | Content                                |
| ------------------ | ---------- | --------- | -------------------------------------- |
| My First Blog Post | 2024-01-15 | Published | This is the content of my blog post... |

## Connecting Notion to GitHub

1. Create an integration in your Notion workspace
2. Share your database with the integration
3. Get the database ID and integration token
4. Add them as GitHub secrets:
   - `NOTION_TOKEN`: Your integration token
   - `NOTION_DATABASE_ID`: Your database ID

## Database ID Location

To find your database ID:

1. Open your database in Notion
2. Copy the URL
3. The ID is the long string after `notion.so/` or in the URL path
4. It looks like: `https://www.notion.so/{workspace}/{database-id}?v={view-id}`

## Integration Token

To get your integration token:

1. Go to developers.notion.com
2. Create a new integration
3. Copy the "Internal Integration Token"
4. Store it securely as `NOTION_TOKEN` in GitHub Secrets
