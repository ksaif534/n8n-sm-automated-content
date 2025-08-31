# Automated Content Posting Workflow

This workflow automates the process of posting content to multiple social media platforms (Facebook, Twitter/X, and LinkedIn) using n8n. It is designed to repurpose content from a Google Sheet and publish it in a platform-specific format.

## Features
- **Google Sheets Trigger**: Monitors a Google Sheet for new rows (content to be posted).
- **Content Repurposing**: Uses a language model (Google Gemini via LangChain) to rewrite content for the target platform (Facebook, Twitter/X, LinkedIn).
- **Platform-Specific Posting**: Posts the repurposed content to the selected platform, with or without associated links, images, or videos.
- **Conditional Logic**: Switches between platforms and posting methods based on the content and available URLs.
- **OAuth2 Integration**: Securely connects to Google Sheets, Facebook, Twitter/X, and LinkedIn using OAuth2 credentials.

## Workflow Steps
1. **Trigger**: The workflow starts when a new row is added to the Google Sheet.
2. **Get Last Row**: Retrieves the latest content entry.
3. **Content Repurposing**: The content, image URL, and video URL are sent to a language model to generate a professional, platform-specific post.
4. **Edit Fields**: Cleans and formats the generated text.
5. **Switch Platform**: Determines which social media platform to post to (Facebook, Twitter/X, LinkedIn).
6. **Conditional Posting**:
   - For each platform, checks if a link is present and selects the appropriate posting method (with or without link).
   - For LinkedIn, retrieves user details before posting.
7. **Post**: Publishes the content to the selected platform using the relevant API.

## Supported Platforms
- **Facebook**: Posts with or without a link using the Facebook Graph API.
- **Twitter/X**: Posts with or without a direct message deep link using the Twitter API.
- **LinkedIn**: Posts with or without a link, using LinkedIn's UGC API and user info.

## Requirements
- n8n instance with required credentials set up for Google Sheets, Facebook, Twitter/X, and LinkedIn.
- A Google Sheet containing columns for content, platform, image_url, video_url, and date.

## Customization
- Update the Google Sheet ID and sheet name in the workflow to match your own.
- Adjust the prompt in the LLM Chain node to change how content is repurposed.
- Modify platform-specific posting logic as needed for your use case.

## Usage
1. Set up OAuth2 credentials for all required services in n8n.
2. Import this workflow into your n8n instance.
3. Update the Google Sheet details and API credentials as needed.
4. Activate the workflow.
5. Add new content rows to your Google Sheet to trigger automated posting.

## File Structure
- `sm-automated-content-posting.json`: The n8n workflow definition.
- `README.md`: This documentation file.

---

**Note:** This workflow is designed for demonstration and automation purposes. Ensure you comply with the terms of service and API rate limits for each platform.
