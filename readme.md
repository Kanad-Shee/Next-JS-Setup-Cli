# Next.js Project Setup CLI ⚡

An interactive CLI tool to quickly setup production-ready Next.js projects with modern tooling. Cross-platform support for Windows, macOS, and Linux.

## 📦 Installation

### Option 1: Global Installation (Recommended)

```bash
npm install -g next-js-setup-cli
```

Then run from anywhere:

```bash
nextjs-setup
# or
create-nextjs-project
```

### Option 2: Use with npx (No Installation)

```bash
npx next-js-setup-cli
```

## ✨ Features

| Feature          | Description                    | What You Get                                                                 |
| ---------------- | ------------------------------ | ---------------------------------------------------------------------------- |
| 🚀 **Next.js**   | Latest Next.js with TypeScript | App Router, Tailwind CSS, ESLint, src/ directory, Import aliases (@/\*)      |
| 🎨 **shadcn/ui** | Beautiful component library    | Pre-configured components system, Default theme, Ready to add components     |
| 🌙 **Theming**   | Dark mode with next-themes     | ThemeProvider component, System theme detection, Easy theme switching        |
| 🦋 **Prettier**  | Code formatting                | Auto-format on save, Tailwind class sorting, Import organization             |
| 🐳 **Docker**    | Containerization setup         | Multi-stage Dockerfile, Optimized production build, .dockerignore configured |

## 🚀 Quick Start

1. Run the CLI:

```bash
npx next-js-setup-cli
```

2. Follow the interactive prompts:
   - Choose setup location (current/new directory)
   - Enter project name (if new directory)
   - Select features you want to include

3. Navigate to your project and start:

```bash
cd your-project-name
npm run dev
```

4. Open [http://localhost:3000](http://localhost:3000)

## 📖 Usage Guide

### Adding shadcn Components

```bash
npx shadcn@latest add button
npx shadcn@latest add card
npx shadcn@latest add dialog
npx shadcn@latest add dropdown-menu
```

### Using Dark Mode (next-themes)

Wrap your app with ThemeProvider in `app/layout.tsx`:

```tsx
import { ThemeProvider } from "@/providers/theme-provider";

export default function RootLayout({ children }) {
  return (
    <html lang='en' suppressHydrationWarning>
      <body>
        <ThemeProvider
          attribute='class'
          defaultTheme='system'
          enableSystem
          disableTransitionOnChange
        >
          {children}
        </ThemeProvider>
      </body>
    </html>
  );
}
```

Create a theme toggle:

```tsx
"use client";
import { useTheme } from "next-themes";

export function ThemeToggle() {
  const { theme, setTheme } = useTheme();
  return (
    <button onClick={() => setTheme(theme === "dark" ? "light" : "dark")}>
      Toggle {theme === "dark" ? "Light" : "Dark"} Mode
    </button>
  );
}
```

### Using Prettier

```bash
# Format all files
npm run format

# Check formatting
npm run format:check
```

### Using Docker

```bash
# Build image
docker build -t my-nextjs-app .

# Run container
docker run -p 3000:3000 my-nextjs-app
```

## 🛠️ What Gets Configured

### Next.js Setup

- ✅ TypeScript with strict mode
- ✅ Tailwind CSS with default config
- ✅ ESLint for code quality
- ✅ App Router (latest Next.js architecture)
- ✅ Organized src/ directory structure
- ✅ Path aliases configured (@/\*)

### Prettier Setup (Optional)

- ✅ Consistent code formatting rules
- ✅ Tailwind CSS class sorting plugin
- ✅ Import sorting and organization
- ✅ .prettierrc and .prettierignore files
- ✅ Format scripts added to package.json

### Docker Setup (Optional)

- ✅ Multi-stage build for optimization
- ✅ Next.js standalone output enabled
- ✅ Production-ready Dockerfile
- ✅ Properly configured .dockerignore

## 💻 Requirements

- Node.js 18.0.0 or higher
- npm, yarn, or pnpm

## 📝 License

MIT

## 🤝 Contributing

Issues and pull requests are welcome! Feel free to contribute to this project.

## 🔗 Links

- [Next.js Documentation](https://nextjs.org/docs)
- [shadcn/ui Documentation](https://ui.shadcn.com)
- [next-themes Documentation](https://github.com/pacocoursey/next-themes)
- [Prettier Documentation](https://prettier.io)

---

Made with ❤️ for the Next.js community

