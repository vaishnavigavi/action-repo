# GitHub Actions Repository

This repository demonstrates the use of GitHub Actions to trigger webhooks for various GitHub events.

## Setup

1. Clone this repository
2. Go to repository settings
3. Add a new secret:
   - Name: `WEBHOOK_URL`
   - Value: Your webhook endpoint URL (e.g., `http://your-domain/webhook`)

## Features

- Triggers webhooks on:
  - Push events to any branch
  - Pull request events (opened, closed, synchronize)
- Automatically detects merge events
- Sends formatted payload to webhook endpoint

## Testing

To test the webhook integration:

1. Make a push to any branch
2. Create a pull request
3. Merge a pull request

Each action will trigger the webhook and send the event data to your configured endpoint.

Test push event - $(date)
Test push event 2 - $(date)
Test push event 3 - $(date)
Test push event 4 - $(date)
Test push event 5 - $(date)
Test push event 6 - $(date) - Testing dark mode UI 