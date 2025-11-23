# BioGenesis Frontend

Frontend application for BioGenesis Genetic Hybridization Platform.

## Installation

```bash
npm install
```

## Run Locally

```bash
npm run dev
```

The app will run on `http://localhost:5173`

## Environment Variables

Create a `.env` file (for local development):

```
VITE_API_BASE=http://localhost:5000/api
```

For production, set `VITE_API_BASE` in your deployment platform (Vercel, Netlify, etc.)

## Build for Production

```bash
npm run build
```

Output will be in the `dist` folder.

## Deployment

See `VERCEL_DEPLOY.md` for detailed Vercel deployment instructions.

## Tech Stack

- React 18
- Vite
- Tailwind CSS
- Firebase (Authentication & Firestore)

