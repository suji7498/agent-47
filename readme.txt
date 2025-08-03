=== Agent-47 ===
Contributors: surajjadhao
Tags: chatbot, n8n, automation, ai, webhook, integration, customer-support, lead-generation
Requires at least: 5.8
Tested up to: 6.8
Stable tag: 1.0.0
Requires PHP: 7.4
License: GPLv2 or later
License URI: https://www.gnu.org/licenses/gpl-2.0.html

A flexible WordPress plugin that integrates with n8n workflows to create intelligent chatbots for your website.

== Description ==

**Agent-47** is a powerful and flexible plugin that allows you to create intelligent chatbots for your WordPress website by integrating with n8n workflows.

= Key Features =

* 🤖 **Flexible n8n Integration**: Works with any n8n workflow
* 🎨 **Customizable UI**: 5 different themes and multiple positions
* 🔧 **Easy Setup**: Simple configuration and testing tools
* 📱 **Responsive Design**: Works on desktop and mobile
* 🔒 **Secure**: Built-in security features and authentication support
* 🐛 **Debug Tools**: Comprehensive debugging and testing utilities

= Use Cases =

* **AI Chatbots**: Integrate with AI services (OpenAI, Google Gemini, etc.)
* **Customer Support**: Create intelligent customer support bots
* **Lead Generation**: Build lead qualification and collection systems
* **Business Automation**: Appointment scheduling, order status inquiries
* **Custom Integrations**: API integrations, database queries, external services

= Quick Start =

1. **Install and activate** the plugin
2. **Import an n8n workflow template** (included with the plugin)
3. **Configure your webhook URL** in WordPress admin
4. **Test the connection** and start chatting!

= n8n Workflow Templates =

The plugin includes ready-to-use n8n workflow templates:
* `n8n-workflow-template.json` - Complete template with proper response formatting
* `n8n-simple-example.json` - Simple example that works immediately

= Response Format Support =

Your n8n workflow can respond in multiple formats:

**JSON Object (Recommended):**
```json
{
  "message": "Your response message here",
  "success": true,
  "timestamp": "2024-01-01 12:00:00"
}
```

**Simple JSON:**
```json
{
  "message": "Your response message here",
  "success": true
}
```

**Plain String:**
```
Your response message here
```

= Customization Options =

* **5 Color Themes**: Sky Blue, Black, Pinkish, Green, Purple
* **4 Positions**: Bottom-right, bottom-left, top-right, top-left
* **Custom Title**: Change the chatbot title
* **Authentication**: Optional token-based authentication
* **HTTP Methods**: Support for POST, GET, PUT, DELETE, PATCH

= Security Features =

* Input sanitization and validation
* CSRF protection
* Rate limiting support
* Secure webhook communication
* Optional authentication

= Debug Tools =

* Built-in connection testing
* Detailed error logging
* Response analysis
* Debug scripts for troubleshooting

For detailed setup instructions, see the [Setup Guide](https://wordpress.org/plugins/agent-47/) or check the plugin documentation.

== Installation ==

= Automatic Installation (Recommended) =

1. Go to **Plugins > Add New** in your WordPress admin
2. Search for "Agent-47"
3. Click **Install Now**
4. Click **Activate**

= Manual Installation =

1. Download the plugin ZIP file
2. Go to **Plugins > Add New > Upload Plugin**
3. Choose the downloaded ZIP file
4. Click **Install Now**
5. Click **Activate**

= After Installation =

1. Go to **Settings > Chatbot n8n**
2. Enter your n8n webhook URL
3. Test the connection
4. Customize the chatbot appearance

= n8n Setup =

1. Import one of the provided workflow templates into n8n
2. Configure your AI agent or processing logic
3. Activate the workflow
4. Copy the webhook URL to WordPress

== Frequently Asked Questions ==

= What is n8n? =

n8n is a powerful workflow automation tool that allows you to connect different services and create automated workflows. It's perfect for building intelligent chatbots.

= Do I need to know how to code? =

No! The plugin includes ready-to-use n8n workflow templates that you can import and customize without coding.

= Can I use this with any AI service? =

Yes! Since it integrates with n8n, you can connect to any AI service that n8n supports, including OpenAI, Google Gemini, Claude, and many others.

= Is this plugin secure? =

Yes, the plugin includes multiple security features including input sanitization, CSRF protection, and secure webhook communication.

= Can I customize the chatbot appearance? =

Yes! You can choose from 5 different themes, 4 different positions, and customize the chatbot title.

= What if my n8n workflow doesn't work? =

The plugin includes comprehensive debugging tools to help you troubleshoot any issues. Check the error logs and use the built-in test connection feature.

= Can I use multiple chatbots? =

Yes! You can create multiple chatbot instances by using different n8n workflows with different webhook paths.

= Is there a free version? =

Yes, this plugin is completely free and open source under the GPL license.

== Screenshots ==

1. Chatbot widget on a website
2. WordPress admin settings page
3. n8n workflow example
4. Customization options
5. Debug and testing tools

== Changelog ==

= 1.0.0 =
* Initial release
* Basic webhook integration
* Customizable UI themes
* Debug and testing tools
* Comprehensive documentation
* n8n workflow templates
* Multiple response format support
* Security features
* Mobile responsive design

== Upgrade Notice ==

= 1.0.0 =
Initial release of Agent-47. This plugin provides a complete solution for integrating n8n workflows with WordPress chatbots. 