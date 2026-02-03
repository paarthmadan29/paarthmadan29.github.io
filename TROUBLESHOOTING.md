# Troubleshooting Guide

## Authentication Issues

### Problem: DNS Resolution Error for auth.decapcms.org

**Symptoms**:

- Error message: "This site can't be reached"
- DNS_PROBE_POSSIBLE error
- Cannot authenticate through the admin panel

**Solutions**:

1. **Try the simplified configuration**:

   - Rename `admin/config-simple.yml` to `admin/config.yml`
   - This removes the custom auth endpoints that might be causing issues

2. **Clear browser cache and cookies**:

   - Hard refresh (Ctrl+F5 or Cmd+Shift+R)
   - Clear site data for your github.io domain

3. **Try incognito/private browsing mode**:

   - This eliminates cached authentication data

4. **Check network connectivity**:
   - Ensure you can access other websites
   - Try accessing the site from a different network

### Alternative Authentication Methods

If the GitHub backend continues to have issues, consider these alternatives:

#### Option 1: Use Git Gateway (requires Netlify)

1. Deploy your site to Netlify
2. Enable Git Gateway in Netlify settings
3. Update config.yml to use `git-gateway` backend

#### Option 2: Local Development

1. Clone your repository locally
2. Run `hugo server` for local development
3. Edit files directly in your local editor
4. Push changes to GitHub

#### Option 3: Direct GitHub Editing

1. Go to your GitHub repository
2. Navigate to the posts folder
3. Create/edit files directly in the GitHub web interface
4. GitHub will automatically deploy to your site

## Testing Authentication

To test if authentication is working:

1. Visit your admin panel: `https://paarthmadan29.github.io/admin/`
2. Click "Access Editor"
3. You should be redirected to GitHub for authentication
4. After successful authentication, you should see the CMS interface

## Common Error Messages

### "Failed to load config file"

- Ensure `admin/config.yml` exists and is properly formatted
- Check for YAML syntax errors

### "Authentication failed"

- Verify you have write access to the repository
- Try signing out of GitHub and signing back in
- Check if your GitHub token has expired

### "Repository not found"

- Verify the repository name in config.yml is correct
- Ensure the repository exists and is accessible

## Getting Help

If issues persist:

1. Check browser developer console for specific error messages
2. Verify your GitHub repository settings
3. Ensure GitHub Pages is properly configured
4. Confirm you have the necessary permissions on the repository
