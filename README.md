# Deno + SvelteKit Dinosaur App Tutorial

A tutorial project demonstrating how to build a full-stack web application using Deno and SvelteKit. This project showcases modern web development practices with TypeScript, server-side rendering, and API routes.

## Make it your own!

You can deploy your own version of this svelte app to Deno Deploy immediately.
Just click the button to clone and deploy.

[![Deploy on Deno](https://deno.com/button)](https://app.deno.com/new?clone=https://github.com/denoland/tutorial-with-svelte)


## Tech Stack

- **Runtime**: [Deno](https://deno.com/)
- **Framework**: [SvelteKit](https://kit.svelte.dev/)
- **Language**: TypeScript
- **Build Tool**: Vite
- **Adapter**: Deno SvelteKit Adapter

## Project Structure

```text
tutorial-with-svelte/
├── src/
│   ├── routes/
│   │   ├── +layout.svelte          # Global layout
│   │   ├── +page.svelte            # Homepage - dinosaur list
│   │   ├── +page.ts                # Homepage data loader
│   │   ├── [dinosaur]/             # Dynamic route for individual dinosaurs
│   │   │   ├── +page.svelte        # Dinosaur detail page
│   │   │   └── +page.ts            # Dinosaur data loader
│   │   └── api/
│   │       ├── data.json           # Dinosaur database (3000+ entries)
│   │       └── dinosaurs/
│   │           └── +server.js      # API endpoint for dinosaur data
│   ├── app.css                     # Global styles
│   ├── app.html                    # HTML template
│   └── lib/
├── static/                         # Static assets
├── deno.json                       # Deno configuration
├── package.json                    # NPM scripts for Vite
├── svelte.config.js               # SvelteKit configuration
└── vite.config.ts                 # Vite configuration
```

## Getting Started

### Installation & Setup

1. Clone or download this project and install dependencies

```bash
git clone https://github.com/denoland/tutorial-with-svelte.git
cd tutorial-with-svelte
deno install
```

2. Run the dev server

```bash
deno task dev
```

3. Open your browser and navigate to [http://localhost:5173](http://localhost:5173)

## Available Scripts

```bash
# Start development server
deno task dev

# Build for production
deno task build

# Preview production build
deno task preview
```

## How It Works

### 1. Homepage (`/`)

- Loads all dinosaurs from the API endpoint
- Displays them as clickable links
- Uses SvelteKit's `load` function for server-side data fetching

### 2. API Routes (`/api/dinosaurs`)

- Serves dinosaur data from a JSON file
- Uses SvelteKit's server routes feature
- Returns data in JSON format

### 3. Dynamic Routes (`/[dinosaur]`)

- Matches any dinosaur name in the URL
- Fetches specific dinosaur data
- Displays detailed information with a back link
