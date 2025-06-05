# GitHub Webhook Events Monitor - Action Repository

This repository is part of the GitHub Webhook Events Monitor system. It contains the GitHub Actions workflow that triggers webhook events for monitoring.

## Purpose

This repository is designed to:
- Trigger webhook events (push, pull requests, merges)
- Send event data to the webhook server
- Test the monitoring system

## Setup

1. **Clone this repository**
   ```bash
   git clone https://github.com/yourusername/action-repo.git
   cd action-repo
   ```

2. **Configure GitHub Secrets**
   - Go to your repository settings
   - Navigate to Secrets and Variables > Actions
   - Add the following secret:
     - `WEBHOOK_URL`: Your webhook server URL (e.g., `https://xxxx-xx-xx-xxx-xx.ngrok-free.app/webhook`)

3. **Workflow Configuration**
   The workflow is configured in `.github/workflows/webhook.yml` and will:
   - Trigger on push events
   - Send event data to your webhook server
   - Include author, branch, and timestamp information

## Testing the Webhook

1. **Make a test push**
   ```bash
   # Add a test line to README.md
   echo "Test push event - $(date)" >> README.md
   
   # Commit and push
   git add README.md
   git commit -m "test: trigger push event"
   git push
   ```

2. **Create a Pull Request**
   - Create a new branch
   - Make some changes
   - Create a pull request to main

3. **Merge a Pull Request**
   - Merge the pull request
   - This will trigger a merge event

## Viewing Events

All events triggered from this repository will be displayed in the webhook server's UI at `http://localhost:5050` (when running locally).

## Troubleshooting

If events are not appearing in the UI:
1. Check the GitHub Actions tab to ensure the workflow is running
2. Verify the `WEBHOOK_URL` secret is correctly set
3. Ensure the webhook server is running and accessible
4. Check the webhook server logs for any errors

## Related Repository

This repository works in conjunction with the [webhook-repo](https://github.com/yourusername/webhook-repo), which:
- Receives the webhook events
- Stores them in MongoDB
- Displays them in a beautiful dark mode UI

## Contributing

Feel free to submit issues and enhancement requests!