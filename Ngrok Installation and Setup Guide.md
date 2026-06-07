# Ngrok Installation and Setup Guide (macOS)

## What is ngrok?

ngrok allows you to securely expose a local web server running on your Mac to the internet using a public URL.

Common use cases:

* Expose local web applications
* Test webhooks
* Share development environments
* Connect local AI applications (Ollama, Next.js, etc.) to external services

---

## Prerequisites

* macOS
* Homebrew installed

Verify Homebrew:

```bash
brew --version
```

---

## Step 1: Install ngrok

Install ngrok using Homebrew:

```bash
brew install ngrok/ngrok/ngrok
```

Verify installation:

```bash
ngrok version
```

Expected output:

```text
ngrok version 3.x.x
```

---

## Step 2: Create an ngrok Account

1. Visit https://ngrok.com
2. Create a free account
3. Login to the dashboard
4. Copy your Authentication Token

---

## Step 3: Configure Authentication

Run:

```bash
ngrok config add-authtoken YOUR_AUTH_TOKEN
```

Example:

```bash
ngrok config add-authtoken 2abc123xyz...
```

You should see:

```text
Authtoken saved to configuration file
```

---

## Step 4: Start a Local Application

Example: Next.js

```bash
npm run dev
```

Default URL:

```text
http://localhost:3000
```

---

## Step 5: Expose Your Local App

Open a new terminal window:

```bash
ngrok http 3000
```

Output:

```text
Forwarding  https://abcd-1234.ngrok-free.app -> http://localhost:3000
```

ngrok generates:

* HTTP URL
* HTTPS URL

Use the HTTPS URL for sharing.

---

## Step 6: Inspect Requests

ngrok provides a local dashboard:

```text
http://127.0.0.1:4040
```

You can inspect:

* Request headers
* Request body
* Response body
* Response status codes

Useful for webhook debugging.

---

## Example: Next.js + Local Ollama

Start Ollama:

```bash
ollama serve
```

Verify:

```bash
curl http://localhost:11434/api/tags
```

Start Next.js:

```bash
npm run dev
```

Expose Next.js:

```bash
ngrok http 3000
```

Example URL:

```text
https://my-agent.ngrok-free.app
```

You can now access your local AI application from anywhere.

---

## Example: Expose Ollama Directly

Expose Ollama API:

```bash
ngrok http 11434
```

Generated URL:

```text
https://abcd.ngrok-free.app
```

Test:

```bash
curl https://abcd.ngrok-free.app/api/tags
```

Note:
Exposing Ollama publicly is not recommended without authentication.

---

## Useful Commands

### Show Version

```bash
ngrok version
```

### View Configuration

```bash
ngrok config check
```

### Start HTTP Tunnel

```bash
ngrok http 3000
```

### Start HTTPS Tunnel

```bash
ngrok http https://localhost:3000
```

### Start TCP Tunnel

```bash
ngrok tcp 22
```

---

## Common Troubleshooting

### ngrok command not found

Verify installation:

```bash
brew list ngrok
```

Restart terminal:

```bash
source ~/.zshrc
```

### Authentication Error

Reconfigure token:

```bash
ngrok config add-authtoken YOUR_TOKEN
```

### Port Already in Use

Find process:

```bash
lsof -i :3000
```

Kill process:

```bash
kill -9 <PID>
```

---

## Recommended Development Setup

Terminal 1:

```bash
ollama serve
```

Terminal 2:

```bash
npm run dev
```

Terminal 3:

```bash
ngrok http 3000
```

Architecture:

```text
Internet
    │
    ▼
ngrok Public URL
    │
    ▼
Next.js App (localhost:3000)
    │
    ▼
Ollama (localhost:11434)
```

This setup is ideal for developing and demonstrating local AI agents powered by Ollama and Next.js.
