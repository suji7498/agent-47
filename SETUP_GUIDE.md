# Agent-47 Setup Guide

## Overview
This guide will help you set up a WordPress chatbot that integrates with n8n workflows. The plugin is designed to be flexible and work with any n8n workflow that follows the standard response format.

**Developer:** [Suraj Jadhao](https://www.linkedin.com/in/suraj-jd/)  
**GitHub:** [suji7498](https://github.com/suji7498)

## Prerequisites
- WordPress site with admin access
- n8n instance (local or cloud)
- Basic understanding of n8n workflows

## Step 1: Install the WordPress Plugin

1. **Upload the plugin** to your WordPress site
2. **Activate the plugin** from WordPress Admin → Plugins
3. **Go to Settings** → Agent-47

## Step 2: Set Up n8n Workflow

### Option A: Import the Template (Recommended)
1. **Download** `n8n-workflow-template.json` from this plugin
2. **Open your n8n instance**
3. **Go to Workflows** → Import from File
4. **Upload the template file**
5. **Customize the workflow** as needed
6. **Activate the workflow**

### Option B: Create Workflow Manually
1. **Create a new workflow** in n8n
2. **Add a Webhook node** with these settings:
   - **HTTP Method**: `POST`
   - **Path**: `wordpress` (or your preferred path)
   - **Respond**: `Using 'Respond to Webhook' Node`
3. **Add your processing nodes** (AI Agent, API calls, etc.)
4. **Add a Set node** to format the response:
   - **Name**: `message`
   - **Value**: `{{ $json.output }}` (or your response field)
   - **Name**: `success`
   - **Value**: `true`
5. **Add a "Respond to Webhook" node**:
   - **Respond With**: `First Incoming Item`
6. **Connect all nodes** and activate the workflow

## Step 3: Configure WordPress Plugin

1. **Go to WordPress Admin** → Settings → Agent-47
2. **Enter your webhook URL**:
   - **Local n8n**: `http://localhost:5678/webhook-test/wordpress`
   - **Cloud n8n**: `https://your-instance.n8n.cloud/webhook-test/wordpress`
3. **Set HTTP Method** to `POST`
4. **Click "Test Connection"** to verify it works

## Step 4: Customize the Chatbot

### Appearance Settings
- **Chatbot Title**: Change the title shown in the chat window
- **Chat Position**: Choose from bottom-right, bottom-left, top-right, top-left
- **Theme**: Select from 5 different color themes
- **Enable/Disable**: Toggle the chatbot on/off

### Advanced Settings
- **Authentication Token**: Add if your webhook requires authentication
- **HTTP Method**: Change if your n8n workflow uses a different method

## Step 5: Test the Integration

1. **Send a test message** through the chatbot
2. **Check n8n logs** to see the incoming request
3. **Verify the response** appears in the chatbot

## Response Format Requirements

Your n8n workflow must respond with one of these formats:

### Format 1: JSON Object (Recommended)
```json
{
  "message": "Your response message here",
  "success": true,
  "timestamp": "2024-01-01 12:00:00",
  "session_id": "optional_session_id"
}
```

### Format 2: Simple JSON
```json
{
  "message": "Your response message here",
  "success": true
}
```

### Format 3: Plain String
```
Your response message here
```

## Troubleshooting

### Common Issues

1. **"Connection failed"**
   - Verify your n8n instance is running
   - Check the webhook URL is correct
   - Ensure the HTTP method matches

2. **"Webhook not registered"**
   - Verify the webhook path in n8n matches your URL
   - Check that the workflow is active
   - Ensure the webhook node is configured correctly

3. **"Invalid JSON response"**
   - Check your n8n workflow response format
   - Verify the "Respond to Webhook" node is configured properly
   - Use the debug script to test the response

4. **Chatbot shows raw expressions**
   - Ensure your n8n workflow uses "First Incoming Item" or proper JSON format
   - Check that expressions are being evaluated correctly

### Debug Tools

1. **Test Connection**: Use the built-in test in WordPress admin
2. **Debug Script**: Use `debug-webhook.php` for detailed analysis
3. **n8n Logs**: Check your n8n instance logs for errors
4. **WordPress Logs**: Check for entries starting with "WP Chatbot n8n:"

## Advanced Configuration

### Custom Webhook Paths
You can use any webhook path in n8n. Just update your WordPress webhook URL accordingly:
- `https://your-n8n.com/webhook-test/custom-path`
- `https://your-n8n.com/webhook-test/chatbot`
- `https://your-n8n.com/webhook-test/ai-assistant`

### Multiple Chatbots
You can create multiple chatbot instances by:
1. **Creating different n8n workflows** with different paths
2. **Using different webhook URLs** in WordPress
3. **Customizing each chatbot** with different themes and positions

### Authentication
If your n8n webhook requires authentication:
1. **Configure authentication** in your n8n webhook node
2. **Add the token** in WordPress plugin settings
3. **Test the connection** to verify it works

## Security Considerations

1. **Use HTTPS** for production webhooks
2. **Implement authentication** if needed
3. **Validate input** in your n8n workflow
4. **Rate limiting** to prevent abuse
5. **Input sanitization** in your n8n workflow

## Support

If you continue to have issues:
1. **Check the WordPress error logs**
2. **Verify your n8n workflow is working**
3. **Test the webhook URL directly** (using tools like Postman)
4. **Ensure all settings match** between WordPress and n8n
5. **Use the debug tools** provided with the plugin

## Examples

### Simple Echo Workflow
```json
{
  "message": "You said: {{ $json.message }}",
  "success": true
}
```

### AI Agent Workflow
```json
{
  "message": "{{ $json.output }}",
  "success": true,
  "timestamp": "{{ $now }}"
}
```

### API Integration Workflow
```json
{
  "message": "{{ $json.api_response }}",
  "success": true,
  "data": "{{ $json.additional_data }}"
}
```

This plugin is designed to be flexible and work with any n8n workflow that follows the standard response format. Feel free to customize and extend it for your specific needs! 