# Install Node.js and npm on macOS Using Homebrew

## Prerequisites

Ensure Homebrew is installed.

Check:

```bash
brew --version
```

If Homebrew is not installed, install it:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Verify installation:

```bash
brew --version
```

---

# Install Node.js

Install the latest LTS version of Node.js:

```bash
brew install node
```

This installs:

* Node.js
* npm (Node Package Manager)

---

# Verify Installation

Check Node.js version:

```bash
node -v
```

Example output:

```text
v24.x.x
```

Check npm version:

```bash
npm -v
```

Example output:

```text
11.x.x
```

---

# Verify Installation Location

Find where Node.js is installed:

```bash
which node
```

Find where npm is installed:

```bash
which npm
```

Example output on Apple Silicon Macs:

```text
/opt/homebrew/bin/node
/opt/homebrew/bin/npm
```

---

# Create a Test Project

Create a new folder:

```bash
mkdir node-test
cd node-test
```

Initialize a project:

```bash
npm init -y
```

---

# Test Node.js

Run:

```bash
node -e "console.log('Node.js is working!')"
```

Expected output:

```text
Node.js is working!
```

---

# Update Node.js

Upgrade to the latest version:

```bash
brew upgrade node
```

---

# Uninstall Node.js

If needed:

```bash
brew uninstall node
```

---

# Create Your First Next.js App

Create a new Next.js application:

```bash
npx create-next-app@latest my-app
```

Navigate into the project:

```bash
cd my-app
```

Start the development server:

```bash
npm run dev
```

Open:

```text
http://localhost:3000
```

---

# Useful Commands

| Command               | Description              |
| --------------------- | ------------------------ |
| `node -v`             | Check Node.js version    |
| `npm -v`              | Check npm version        |
| `npm init -y`         | Create package.json      |
| `npm install`         | Install dependencies     |
| `npm run dev`         | Start development server |
| `brew upgrade node`   | Update Node.js           |
| `brew uninstall node` | Remove Node.js           |

---

# Recommended Developer Setup

* Homebrew
* Node.js LTS
* npm
* Git
* VS Code
* GitHub Account
* Vercel for deployment

This setup is sufficient for building modern React, Next.js, AI Agent, and full-stack web applications.
