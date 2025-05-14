# {{ project-title }} Frontend

This is a [SvelteKit](https://kit.svelte.dev) project, powered by [Svelte](https://svelte.dev).

## Quick Reference

| Task                   | Command                                      |
| ---------------------- | -------------------------------------------- |
| Install dependencies   | `pnpm install`                               |
| Run development server | `pnpm dev`                                   |
| Run dev with open tab  | `pnpm dev -- --open`                         |
| Build for production   | `pnpm build`                                 |
| Preview production     | `pnpm preview`                               |
| Lint code              | `pnpm lint`                                  |
| Run tests              | `pnpm test`                                  |
| Build Docker image     | `docker build -t {{ project-name }} .`        |
| Run Docker container   | `docker run -p 5173:5173 {{ project-name }}`  |

## Getting Started

First, install dependencies:

```bash
pnpm install
```

Then, run the development server:

```bash
pnpm dev

# or start the server and open the app in a new browser tab
pnpm dev -- --open
```

Open [http://localhost:5173](http://localhost:5173) with your browser to see the result.

You can start editing the page by modifying files in `src/routes`. The page auto-updates as you edit the files.

## Learn More

To learn more about SvelteKit, take a look at the following resources:

- [Svelte Documentation](https://svelte.dev/docs) - learn about Svelte features and API.
- [SvelteKit Documentation](https://kit.svelte.dev/docs) - learn about SvelteKit features and API.
- [Learn Svelte](https://learn.svelte.dev) - an interactive Svelte tutorial.

You can check out [the SvelteKit GitHub repository](https://github.com/sveltejs/kit) - your feedback and contributions are welcome!

## Deployment Options

### Deploy with Docker on Kubernetes

This project is configured to be deployed as a Docker container on Kubernetes.

To build for production:

```bash
pnpm build
```

You can preview the production build with:

```bash
pnpm preview
```

To build and run the Docker container:

```bash
# Build the Docker image
docker build -t {{ project-name }} .

# Run the container
docker run -p 5173:5173 {{ project-name }}
```

The application will be available at http://localhost:5173.

> To deploy your app, you may need to install an [adapter](https://kit.svelte.dev/docs/adapters) for your target environment. This project currently uses [@sveltejs/adapter-node](https://github.com/sveltejs/kit/tree/master/packages/adapter-node).
