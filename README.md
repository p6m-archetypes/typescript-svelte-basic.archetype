# TypeScript Svelte Application Archetype

![Latest Release](https://img.shields.io/github/v/release/p6m-archetypes/typescript-svelte-basic.archetype?style=flat-square&label=Latest%20Release&color=blue)

Modern Svelte application archetype with TypeScript, compiled components, and Kubernetes deployment ready.

## 🎯 What This Generates

This archetype creates a Svelte application with:

- **⚡ Svelte 4**: Compiled framework with minimal runtime overhead
- **🎨 TypeScript**: Full type safety with Svelte TypeScript support
- **🔧 Vite**: Lightning-fast build tool with hot module replacement
- **🐳 Container-Ready**: Docker and Kubernetes deployment manifests
- **🧪 Testing**: Vitest and Svelte Testing Library configured
- **📦 Modern Tooling**: ESLint and Prettier for code quality

## 📦 Generated Project Structure

```
my-customer-frontend/
├── src/
│   ├── lib/                # Reusable components and utilities
│   ├── routes/             # SvelteKit routes (if using SvelteKit)
│   ├── app.html            # HTML template
│   └── main.ts             # Application entry point
├── static/                 # Static assets
├── tests/                  # Test files
├── k8s/                    # Kubernetes manifests
├── Dockerfile
├── svelte.config.js
└── package.json
```

## 🚀 Quick Start

### Prerequisites

- [Archetect](https://archetect.github.io/) CLI tool
- Node.js 18+
- Docker (optional, for containerized deployment)

### Generate & Run

```bash
archetect render https://github.com/p6m-archetypes/typescript-svelte-basic.archetype.git#v1

# Example prompt answers:
# organization-name: acme-inc
# project-title: Customer Portal
# project-prefix: customer
# Result: customer-frontend/

cd customer-frontend
npm install
npm run dev

# Access at: http://localhost:5173
```

## 📋 Configuration

| Property | Description | Example |
|----------|-------------|---------|
| `organization-name` | GitHub organization or username | acme-inc |
| `project-title` | Display name for the application | Customer Portal |
| `project-prefix` | Project identifier (suffix '-frontend' added automatically) | customer |

## ✨ Key Features

### 🏛️ Svelte Features

- **Compiled Components**: No virtual DOM - compiles to efficient vanilla JavaScript
- **Reactive Declarations**: Simple `$:` syntax for reactive statements
- **Built-in Animations**: Smooth transitions and animations without libraries
- **Scoped Styles**: Component-scoped CSS by default
- **Stores**: Built-in reactive state management
- **Actions**: Reusable DOM manipulation with use: directives

### 🎨 Developer Experience

- **TypeScript**: Full IDE support and type checking for Svelte components
- **Vite**: Lightning-fast HMR and optimized production builds
- **ESLint**: Configured with Svelte-specific rules
- **Prettier**: Code formatting with Svelte plugin
- **Minimal Boilerplate**: Write less code compared to other frameworks

### 🧪 Testing

- **Vitest**: Fast unit testing framework built on Vite
- **Svelte Testing Library**: Component testing utilities
- **Test Coverage**: Coverage reporting configured
- **E2E Ready**: Can integrate Playwright or Cypress

### 🚢 Deployment

- **Docker**: Production-optimized Nginx-based container
- **Kubernetes**: Deployment and Service manifests
- **Static Output**: Build generates optimized static files
- **Small Bundle Size**: Minimal runtime for fast loading

## 🎯 Use Cases

Ideal for:

1. **Single Page Applications**: Fast, interactive web UIs with minimal overhead
2. **Performance-Critical Apps**: Applications where bundle size and speed matter
3. **Interactive Dashboards**: Data visualization with smooth animations
4. **Component Libraries**: Building reusable component packages
5. **Lightweight Applications**: Projects requiring minimal JavaScript payload

## 📚 What's Inside

### Svelte Compiler

The Svelte compiler transforms your components into highly optimized vanilla JavaScript at build time, resulting in:
- **No Virtual DOM**: Direct DOM manipulation for better performance
- **Small Bundle Size**: Only include what you use
- **Fast Runtime**: Minimal framework overhead

### Reactivity System

Svelte's reactive system is built into the language:
- `$:` reactive declarations automatically update when dependencies change
- Stores for shared state across components
- Two-way binding with `bind:` directives

### Development Tools

- **Svelte Extension**: VS Code extension for syntax highlighting and IntelliSense
- **Svelte DevTools**: Browser extension for debugging components
- **Vite Plugin**: Seamless Svelte integration with Vite

## 🔧 Svelte-Specific Features

### Component Syntax

```svelte
<script lang="ts">
  let count = 0;
  $: doubled = count * 2;  // Reactive declaration
</script>

<button on:click={() => count++}>
  Count: {count}
  Doubled: {doubled}
</button>

<style>
  button { /* Scoped by default */ }
</style>
```

### Performance Benefits

- **Compile-Time Optimization**: Code optimized during build
- **No Runtime Framework**: Minimal JavaScript sent to browser
- **Tree Shaking**: Dead code elimination at compile time
- **Component-Level Code Splitting**: Load only what you need

## 📋 Validation

```bash
npm run build && npm test
```

## 🔗 Related Archetypes

- **[TypeScript Vue.js](../typescript-vuejs-basic.archetype)** - Progressive Vue.js framework
- **[TypeScript Next.js](../typescript-nextjs-basic.archetype)** - React with SSR
- **[TypeScript Angular](../typescript-angular-basic.archetype)** - Full-featured framework

## 📄 License

MIT License

---

**Build blazing-fast UIs with Svelte!** 🚀
