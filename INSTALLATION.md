# Installation Guide - WP Chatbot n8n

## Quick Installation

### Step 1: Prepare the Plugin
1. Ensure all plugin files are in the `wp-chatbot-n8n` folder
2. The folder structure should match the expected WordPress plugin format

### Step 2: Install via WordPress Admin
1. Log into your WordPress admin panel
2. Go to **Plugins > Add New**
3. Click **Upload Plugin** at the top of the page
4. Click **Choose File** and select the plugin folder or ZIP file
5. Click **Install Now**
6. Click **Activate Plugin**

### Step 3: Configure the Plugin
1. Go to **Settings > Chatbot n8n**
2. Enter your n8n webhook URL
3. Configure other settings as needed
4. Click **Save Settings**

## Manual Installation

If the WordPress plugin installer doesn't work:

1. **Upload Files**: Upload the `wp-chatbot-n8n` folder to `/wp-content/plugins/`
2. **Activate**: Go to **Plugins** in WordPress admin and activate "WP Chatbot n8n"
3. **Configure**: Follow Step 3 above

## Troubleshooting Installation Issues

### Common Problems:

1. **"Plugin file does not exist"**
   - Ensure the main plugin file `wp-chatbot-n8n.php` is in the root of the plugin folder
   - Check that the plugin header is properly formatted

2. **"Plugin could not be activated"**
   - Check WordPress error logs
   - Ensure PHP version is 7.4 or higher
   - Verify all required files are present

3. **"Plugin appears but doesn't work"**
   - Check browser console for JavaScript errors
   - Verify n8n webhook URL is correct
   - Test webhook connection in plugin settings

### File Permissions:
- Plugin folder: 755
- Plugin files: 644
- Ensure web server can read all files

### Required Files Check:
```
wp-chatbot-n8n/
├── wp-chatbot-n8n.php          ✓ Required
├── uninstall.php               ✓ Required
├── includes/                   ✓ Required
│   ├── class-chatbot-core.php
│   ├── class-chatbot-api.php
│   ├── class-chatbot-webhook.php
│   ├── class-chatbot-database.php
│   └── class-chatbot-security.php
├── admin/                      ✓ Required
│   ├── class-chatbot-admin.php
│   ├── js/admin-script.js
│   └── css/admin-style.css
├── public/                     ✓ Required
│   ├── class-chatbot-public.php
│   ├── js/chatbot-frontend.js
│   └── css/chatbot-style.css
└── README.md                   ✓ Recommended
```

## Post-Installation Setup

1. **Test the Webhook**: Use the "Test Connection" button in settings
2. **Check Frontend**: Visit your website to see the chatbot widget
3. **Customize**: Adjust styling and positioning as needed
4. **Monitor**: Check WordPress error logs for any issues

## Support

If you encounter issues:
1. Check the main README.md file
2. Review WordPress error logs
3. Verify n8n workflow is working
4. Test webhook independently 