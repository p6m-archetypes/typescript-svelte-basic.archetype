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

## Promoting Images

Upon each commit to main, the Docker image is built and deployed to the dev Kubernetes cluster automatically. However, the process to promote an image to stg or prd requires a couple of manual button presses, allowing you to control when to deploy images to other environments.

1. Launch a run of [**Cut Release Tag**](.github/workflows/cut-tag.yaml) — this will bump the version number of the application, publish a new docker image to Artifactory with the necessary tags, and create a new Github release from that tag. Make sure to select the appropriate level to bump, conforming with [semantic versioning](https://semver.org/).
2. Launch a run of [**Promote Tag**](.github/workflows/promote.yaml) — this will take an existing docker image and promote it to the specified environment. Make sure to enter the Github tag you wish to promote (created by **Cut Release Tag** from step one) and the environment to which you wish to promote the image.
