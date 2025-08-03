# Agent-47 aka wp-chatbot-n8n

A flexible WordPress plugin that integrates with n8n workflows to create intelligent chatbots for your website.

**Developer:** [Suraj Jadhao](https://www.linkedin.com/in/suraj-jd/)  
**GitHub:** [suji7498](https://github.com/suji7498)

## Features

- 🤖 **Flexible n8n Integration**: Works with any n8n workflow
- 🎨 **Customizable UI**: 5 different themes and multiple positions
- 🔧 **Easy Setup**: Simple configuration and testing tools
- 📱 **Responsive Design**: Works on desktop and mobile
- 🔒 **Secure**: Built-in security features and authentication support
- 🐛 **Debug Tools**: Comprehensive debugging and testing utilities

## Quick Start

### 1. Install the Plugin
1. Upload the plugin to your WordPress site
2. Activate it from WordPress Admin → Plugins
3. Go to Settings → Chatbot n8n

### 2. Set Up n8n Workflow
1. Import the provided `n8n-workflow-template.json` or create your own
2. Configure your AI agent or processing logic
3. Activate the workflow

### 3. Configure WordPress
1. Enter your n8n webhook URL
2. Test the connection
3. Customize the chatbot appearance

## n8n Workflow Template

The plugin includes a ready-to-use n8n workflow template (`n8n-workflow-template.json`) that you can import and customize.

### Template Features:
- Webhook endpoint for WordPress integration
- Response formatting for compatibility
- Easy customization for different use cases

## Response Format Support

The plugin supports multiple response formats from n8n:

### JSON Object (Recommended)
```json
{
  "message": "Your response message here",
  "success": true,
  "timestamp": "2024-01-01 12:00:00",
  "session_id": "optional_session_id"
}
```

### Simple JSON
```json
{
  "message": "Your response message here",
  "success": true
}
```

### Plain String
```
Your response message here
```

## Customization Options

### Appearance
- **Chatbot Title**: Customize the title shown in the chat window
- **Position**: Choose from bottom-right, bottom-left, top-right, top-left
- **Theme**: Select from 5 different color themes:
  - Sky Blue (Default)
  - Black (Professional)
  - Pinkish (Creative)
  - Green (Nature/Health)
  - Purple (Creative/Arts)

### Functionality
- **Enable/Disable**: Toggle the chatbot on/off
- **HTTP Method**: Support for POST, GET, PUT, DELETE, PATCH
- **Authentication**: Optional token-based authentication
- **Timeout**: Configurable request timeout (45 seconds default)

## Use Cases

### AI Chatbots
- Integrate with AI services (OpenAI, Google Gemini, etc.)
- Create intelligent customer support bots
- Build FAQ and knowledge base assistants

### Business Automation
- Lead qualification and collection
- Appointment scheduling
- Order status inquiries
- Customer feedback collection

### Custom Integrations
- API integrations
- Database queries
- External service connections
- Custom business logic

## Installation

### Manual Installation
1. Download the plugin files
2. Upload to `/wp-content/plugins/wp-chatbot-n8n/`
3. Activate the plugin through the 'Plugins' menu in WordPress

### Requirements
- WordPress 5.0 or higher
- PHP 7.4 or higher
- n8n instance (local or cloud)

## Configuration

### Basic Setup
1. Go to **WordPress Admin** → **Settings** → **Chatbot n8n**
2. Enter your **n8n Webhook URL**
3. Select **HTTP Method** (usually POST)
4. Click **"Test Connection"** to verify

### Advanced Configuration
- **Authentication Token**: Add if your webhook requires authentication
- **Custom Themes**: Modify CSS for custom styling
- **Multiple Instances**: Use different webhook URLs for multiple chatbots

## Troubleshooting

### Common Issues

1. **Connection Failed**
   - Verify your n8n instance is running
   - Check the webhook URL is correct
   - Ensure the HTTP method matches

2. **Webhook Not Registered**
   - Verify the webhook path in n8n matches your URL
   - Check that the workflow is active
   - Ensure the webhook node is configured correctly

3. **Invalid JSON Response**
   - Check your n8n workflow response format
   - Verify the "Respond to Webhook" node is configured properly
   - Use the debug script to test the response

### Debug Tools

The plugin includes several debugging tools:

1. **Built-in Test**: Use the "Test Connection" button in WordPress admin
2. **Debug Script**: Use `debug-webhook.php` for detailed analysis
3. **Error Logging**: Check WordPress error logs for detailed information
4. **Response Analysis**: Automatic response format detection and normalization

## Security

### Built-in Security Features
- Input sanitization and validation
- CSRF protection
- Rate limiting support
- Secure webhook communication
- Optional authentication

### Best Practices
- Use HTTPS for production webhooks
- Implement authentication for sensitive data
- Validate input in your n8n workflow
- Monitor webhook usage and implement rate limiting
- Keep the plugin updated

## Development

### File Structure
```
wp-chatbot-n8n/
├── admin/                 # Admin interface
├── assets/               # Static assets (CSS, JS, images)
├── includes/             # Core plugin classes
├── public/               # Frontend functionality
├── languages/            # Translation files
├── templates/            # Template files
├── n8n-workflow-template.json  # n8n workflow template
├── SETUP_GUIDE.md        # Detailed setup guide
├── WEBHOOK_SETUP.md      # Webhook-specific setup
└── README.md             # This file
```

### Hooks and Filters
The plugin provides several hooks for customization:

```php
// Modify webhook response
add_filter('wp_chatbot_n8n_response', 'custom_response_handler', 10, 2);

// Add custom validation
add_filter('wp_chatbot_n8n_validate_message', 'custom_validation', 10, 1);

// Modify chatbot settings
add_filter('wp_chatbot_n8n_settings', 'custom_settings', 10, 1);
```

## Support

### Documentation
- [Setup Guide](SETUP_GUIDE.md) - Comprehensive setup instructions
- [Webhook Setup](WEBHOOK_SETUP.md) - n8n webhook configuration
- [Installation Guide](INSTALLATION.md) - Installation instructions

### Getting Help
1. Check the troubleshooting section above
2. Review the setup guides
3. Check WordPress error logs
4. Use the debug tools provided

## Changelog

### Version 1.0.0
- Initial release
- Basic webhook integration
- Customizable UI themes
- Debug and testing tools
- Comprehensive documentation

## License

This plugin is released under the GPL v2 or later license.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Credits

- Built for WordPress and n8n integration
- Designed for flexibility and ease of use
- Includes comprehensive documentation and examples

---

**Need help?** Check out the [Setup Guide](SETUP_GUIDE.md) for detailed instructions, or use the built-in debug tools to troubleshoot any issues.

## Developer Information

- **Developer:** Suraj Jadhao
- **LinkedIn:** [https://www.linkedin.com/in/suraj-jd/](https://www.linkedin.com/in/suraj-jd/)

- **GitHub:** [https://github.com/suji7498](https://github.com/suji7498) 
