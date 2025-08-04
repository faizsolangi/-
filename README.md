# n8n YouTube Notifier

Automated workflow to send email notifications for new YouTube video uploads using n8n, YouTube Data API v3, and Gmail.

## Features
- Checks for new videos every 5 minutes.
- Sends instant Gmail notifications with video title and link.
- Prevents duplicate notifications using video ID tracking.
- Deployable in hours with error handling.

## Tech Stack
- **n8n**: Workflow automation platform.
- **YouTube Data API v3**: Fetches latest videos (OAuth2 authentication).
- **Gmail API**: Sends email notifications (OAuth2 authentication).

## Setup Instructions
1. **Prerequisites**:
   - n8n Cloud account (`https://faizsolangi.app.n8n.cloud` or your instance).
   - Google Cloud project with YouTube Data API v3 and Gmail API enabled.
   - OAuth2 credentials for YouTube (`https://www.googleapis.com/auth/youtube.readonly`) and Gmail (`https://www.googleapis.com/auth/gmail.send`).

2. **Import Workflow**:
   - Download `youtube_notification_workflow.json`.
   - In n8n, go to **New** > **Import Workflow** > Paste JSON.
   - Update:
     - **Get Latest Video**: Set `channelId` to your YouTube channel ID (e.g., `UCxxxxx`).
     - **Send Notification**: Set `toEmail` to the recipient’s email.
     - Link **YouTube OAuth2** and **Gmail OAuth2** credentials.

3. **Configure Google Cloud**:
   - Create OAuth2 Client ID in Google Cloud Console.
   - Add redirect URI: `https://<your-n8n-instance>.app.n8n.cloud/oauth2/callback`.
   - Add test user: Your Google account (e.g., `outreach@solinnovate.io`).
   - Enable scopes: `https://www.googleapis.com/auth/youtube.readonly`, `https://www.googleapis.com/auth/gmail.send`.

4. **Test and Activate**:
   - Execute workflow manually to verify email delivery.
   - Toggle **Active** for periodic checks.

## Files
- `youtube_notification_workflow.json`: n8n workflow export.
- `youtube_workflow_screenshot.png`: Workflow visualization.

## Notes
- **API Quota**: YouTube `search.list` uses 100 units/call (10,000 units/day free). Use a 15-minute schedule (~9,600 units) to stay within limits.
- **Customization**: Add HTML email formatting or Webhook triggers as needed.
- **Support**: Contact for deployment or tweaks.

## Author
Faiz Solangi | [Upwork Profile](https://www.upwork.com/freelancers/~your-upwork-id) | outreach@solinnovate.io

---

Built for instant, reliable YouTube notifications. Ready to customize for your needs!
