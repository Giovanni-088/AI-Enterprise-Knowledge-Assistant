# Slack Integration

## Objective

Integrate Slack with n8n to allow employees to communicate with the AI assistant through a secure webhook.

---

# Components

- Slack App
- Bot User
- OAuth 2.0
- Event Subscriptions
- Slack Events API
- n8n Webhook
- Cloudflare Tunnel

---

# Architecture

Employee

↓

Slack

↓

Slack Events API

↓

Cloudflare Tunnel

↓

n8n Webhook

↓

Workflow Processing

---

# OAuth

The application uses a Bot User OAuth Token to authenticate requests sent to the Slack API.

Environment variable:

SLACK_BOT_TOKEN

---

# Security

Incoming requests are signed by Slack.

The application stores the Signing Secret for future request verification.

Environment variable:

SLACK_SIGNING_SECRET

---

# Event Subscriptions

Current subscribed event:

- app_mention

The assistant only responds when explicitly mentioned.

Example:

@AI Enterprise Knowledge Assistant
How do I deploy a new workflow?

This prevents the assistant from processing every message in a channel.

---

# Current Status

Completed

- Slack App
- OAuth
- Bot User
- Event Subscription
- Webhook Verification
