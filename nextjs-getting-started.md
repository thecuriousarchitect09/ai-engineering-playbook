# Next.js Getting Started Guide

## Prerequisites

Before creating a Next.js project, ensure the following are installed:

* Node.js (LTS Version)
* npm (comes with Node.js)
* Visual Studio Code (recommended)

Verify installation:

```bash
node -v
npm -v
```

---

## Step 1: Create a New Next.js Project

Open Terminal and run:

```bash
npx create-next-app@latest my-next-app
```

Example selections:

```text
✔ Would you like to use TypeScript? No
✔ Would you like to use ESLint? Yes
✔ Would you like to use Tailwind CSS? Yes
✔ Would you like your code inside a src/ directory? Yes
✔ Would you like to use App Router? Yes
✔ Would you like to use Turbopack? Yes
✔ Customize import alias? No
```

---

## Step 2: Navigate to the Project

```bash
cd my-next-app
```

---

## Step 3: Start the Development Server

```bash
npm run dev
```

Open:

```text
http://localhost:3000
```

You should see the Next.js welcome page.

---

## Step 4: Edit the Home Page

Open:

```text
src/app/page.tsx
```

Replace the content with:

```tsx
export default function Home() {
  return (
    <main className="p-10">
      <h1 className="text-4xl font-bold">
        My First Next.js App
      </h1>

      <p className="mt-4">
        Running successfully 🚀
      </p>
    </main>
  );
}
```

Save the file and the browser will automatically refresh.

---

## Step 5: Understanding the Project Structure

```text
my-next-app/
├── src/
│   └── app/
│       ├── page.tsx
│       ├── layout.tsx
│       └── globals.css
├── public/
├── package.json
├── next.config.ts
└── node_modules/
```

### Important Files

| File         | Purpose                  |
| ------------ | ------------------------ |
| page.tsx     | Home page                |
| layout.tsx   | Shared layout            |
| globals.css  | Global styling           |
| package.json | Dependencies and scripts |
| public/      | Static assets            |

---

## Step 6: Create Another Page

Create:

```text
src/app/about/page.tsx
```

Add:

```tsx
export default function About() {
  return (
    <div>
      <h1>About Page</h1>
    </div>
  );
}
```

Visit:

```text
http://localhost:3000/about
```

---

## Step 7: Create a Reusable Component

Create:

```text
src/components/Header.tsx
```

```tsx
export default function Header() {
  return (
    <header>
      <h2>My Website</h2>
    </header>
  );
}
```

Use it in page.tsx:

```tsx
import Header from "@/components/Header";

export default function Home() {
  return (
    <>
      <Header />
      <h1>Home Page</h1>
    </>
  );
}
```

---

## Step 8: Build for Production

```bash
npm run build
```

Run production mode:

```bash
npm start
```

---

