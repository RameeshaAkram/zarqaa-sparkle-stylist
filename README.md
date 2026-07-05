# Welcome to your Lovable project

## Project info

**URL**: https://lovable.dev/projects/8057f6d7-71af-4a8b-8180-5ad0d913f8b9

## How can I edit this code?

There are several ways of editing your application.

# ZarqaaCloset AI Fashion Assistant

ZarqaaCloset is an AI-powered fashion assistant for eastern wear and jewelry. The frontend is a React + Vite app with a storefront-style home page, an AI stylist flow, a conversational FAQ assistant, and an algorithm visualization screen. It connects to Supabase for product data and edge functions.

## Features

- AI stylist for occasion, preference, and budget-based outfit recommendations
- Conversational fashion and FAQ chat
- Product catalog driven by Supabase
- Interactive algorithm visualization for A*, genetic algorithms, and expert-system rules
- Responsive UI built with shadcn/ui, Tailwind CSS, and Lucide icons

## Tech Stack

- Vite
- React 18
- TypeScript
- React Router
- TanStack Query
- Supabase
- shadcn/ui
- Tailwind CSS

## Project Structure

- `src/pages/Index.tsx` - main landing page and AI stylist experience
- `src/pages/FAQChat.tsx` - FAQ chat interface
- `src/pages/AlgorithmVisualization.tsx` - algorithm walkthrough screen
- `src/integrations/supabase/client.ts` - Supabase client setup
- `supabase/functions/fashion-chat` - FAQ and fashion chat edge function
- `supabase/functions/fashion-recommendations` - outfit recommendation edge function
- `python_backend/` - optional reference Python backend

## Prerequisites

- Node.js 18 or newer
- npm
- A Supabase project with the required environment variables and edge functions

## Setup

1. Install dependencies:

```bash
npm install
```

2. Create a `.env` file in the project root with your Supabase values:

```bash
VITE_SUPABASE_URL=your-supabase-project-url
VITE_SUPABASE_PUBLISHABLE_KEY=your-supabase-anon-or-publishable-key
```

3. Start the development server:

```bash
npm run dev
```

4. Open the app in the local Vite URL shown in the terminal.

## Supabase Requirements

The frontend expects these Supabase edge functions:

- `fashion-chat`
- `fashion-recommendations`

It also expects a public `products` table containing at least these fields:

- `id`
- `name`
- `description`
- `price`
- `category`
- `occasion`
- `image_url`
- `created_at`

The app reads products from Supabase and sends chat/recommendation requests to the edge functions.

## Optional Python Backend

The `python_backend/` folder contains a standalone reference implementation of the same fashion assistant logic. It is not required for the frontend, but you can run it separately if you want to experiment with the Python version.

```bash
cd python_backend
pip install -r requirements.txt
python main.py
```

## Available Routes

- `/` - home and AI stylist entry point
- `/faq` - FAQ chat
- `/algorithms` - algorithm visualization
- `*` - fallback 404 page

## Build

```bash
npm run build
```

## Notes

- The app uses Supabase edge functions for AI responses, so the frontend will not work correctly without the matching backend setup.
- The Python backend references the same fashion assistant concepts but is separate from the Vite app.
