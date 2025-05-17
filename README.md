# BlogSpace

A modern, full-stack blog application built with React, TypeScript, and Supabase. BlogSpace allows users to create, read, update, and delete blog posts with a beautiful, responsive interface.

## Features

- 🔐 User authentication with email/password
- ✍️ Create, edit, and delete blog posts
- 📱 Fully responsive design
- 🎨 Modern UI with Tailwind CSS
- 📝 Rich text content support
- 🔍 Public blog listing with pagination
- ⚡ Real-time updates with Supabase

## Tech Stack

- **Frontend:**
  - React 18
  - TypeScript
  - Tailwind CSS
  - React Router v6
  - React Hook Form
  - Lucide React Icons

- **Backend & Database:**
  - Supabase (PostgreSQL)
  - Row Level Security (RLS)
  - Real-time subscriptions

## Getting Started

1. Clone the repository
2. Install dependencies:
   ```bash
   npm install
   ```

3. Set up environment variables:
   Create a `.env` file in the root directory with your Supabase credentials:
   ```
   VITE_SUPABASE_URL=your_supabase_url
   VITE_SUPABASE_ANON_KEY=your_supabase_anon_key
   ```

4. Start the development server:
   ```bash
   npm run dev
   ```

## Project Structure

```
src/
├── components/     # Reusable UI components
├── context/       # React context providers
├── lib/           # Utility functions and configurations
├── pages/         # Page components
├── types/         # TypeScript type definitions
└── main.tsx       # Application entry point
```

## Database Schema

### Profiles Table
```sql
CREATE TABLE profiles (
  id UUID PRIMARY KEY,
  username TEXT UNIQUE,
  avatar_url TEXT,
  created_at TIMESTAMPTZ
);
```

### Blogs Table
```sql
CREATE TABLE blogs (
  id UUID PRIMARY KEY,
  title TEXT,
  content TEXT,
  user_id UUID,
  created_at TIMESTAMPTZ,
  updated_at TIMESTAMPTZ
);
```

## Authentication

The application uses Supabase Authentication with email/password sign-up. Row Level Security (RLS) policies ensure that:
- Anyone can view blogs and profiles
- Only authenticated users can create blogs
- Users can only edit/delete their own blogs
- Users can only update their own profile

## Deployment

The application can be deployed to any static hosting platform:

1. Build the application:
   ```bash
   npm run build
   ```

2. Deploy the `dist` directory to your hosting platform of choice

## Contributing

1. Fork the repository
2. Create a new branch
3. Make your changes
4. Submit a pull request

 
