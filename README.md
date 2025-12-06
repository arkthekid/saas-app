# Converso – AI Learning Companion Platform

This is the official repository for my Converso AI Learning Companion App.

## Table of Contents
1. [Why I Developed Converso](#why-i-developed-converso)
2. [Features](#features)
3. [Quick Start](#quick-start)
4. [Technologies Involved](#technologies-involved)

---

## Why I Developed Converso

Converso was built from my desire to combine **AI**, **education**, and **full-stack engineering** into a single platform. I wanted to create a personalized, interactive learning experience where users can build their own AI companions tailored to the subjects they want to learn.

Here are the core motivations behind the project:

- **AI-Driven Personalized Learning**: To allow users to create unique tutors with different names, tones, subjects, and teaching styles.
- **Advancing My Full-Stack Skills**: To deepen my understanding of Next.js App Router, server components, API routes, and clean architecture.
- **Authentication & User Security**: To integrate Clerk for seamless user management and protected routes.
- **Database Design**: To work with relational schemas in Supabase/PostgreSQL (companions, sessions, bookmarks).
- **Interactive UI/UX**: To build a clean and responsive interface using TailwindCSS and Shadcn UI.
- **Form Validation & Data Control**: To use React Hook Form + Zod for robust form handling.
- **Real-World SaaS Setup**: To deploy a real, production-ready app on Vercel.
- **Portfolio Growth**: Converso showcases my ability to build a full AI-powered platform from scratch.

---

# Features

(*A full demonstration video is coming soon.*)

### **Authentication with Clerk**
- Email/password login
- Protected routes
- Managed user profiles

### **Build Custom AI Learning Companions**
- Choose name, subject, topic, voice, style, and duration
- Each companion feels unique and tailored to the user

### **AI-Generated Lessons & Chat Sessions**
- Start lessons and interact with the AI companion
- Lessons are contextual and based on the chosen topic

### **Session Tracking**
- View all recently completed sessions
- Track time, subject, companion, and session details

### **Bookmarks**
- Bookmark favorite companions
- Clean relational storage in Supabase

### **My Journey Dashboard**
- View account details
- Track:
  - *Lessons completed*
  - *Companions created*
  - *Bookmarks saved*
- Collapsible accordion sections for organization

### **Responsive UI with Shadcn & Tailwind**
- Beautiful layout
- Mobile optimized
- Clean card and table components

### **Supabase Relational Database**
- Persistent storage for:
  - Companions
  - Sessions
  - Bookmarks
- Indices for optimized performance

### **Robust Form Handling**
- React Hook Form + Zod for validation and clean state management

### **Vercel Deployment**
- Serverless performance
- Instant previews
- CI/CD ready

---

# Quick Start

Follow these steps to run the project locally.

---

## 1. **Prerequisites**

You need:

- Git  
- Node.js  
- npm  
- A Supabase project  
- A Clerk project  
- An OpenAI API key  

---

## 2. **Clone the Repository**

  git clone https://github.com/arkthekid/converso.git
  cd converso

## 3. Install Dependencies

  npm install

## 4. Environment Variables

Create a file named .env.local in the project root and add:

  NEXT_PUBLIC_SUPABASE_URL=
  NEXT_PUBLIC_SUPABASE_ANON_KEY=

  CLERK_PUBLISHABLE_KEY=
  CLERK_SECRET_KEY=

  OPENAI_API_KEY=

## 5. Configure Supabase Database

If you're setting up the database from scratch, run this SQL inside the Supabase SQL Editor:

  create table public.bookmarks (
    id uuid primary key default gen_random_uuid(),
    user_id text not null,
    companion_id uuid not null references public.companions(id) on delete cascade,
    created_at timestamptz default now()
  );

create index bookmarks_user_id_idx on public.bookmarks (user_id);
create index bookmarks_companion_id_idx on public.bookmarks (companion_id);

3. Run the Development Server
  
  npm run dev

# Technologies Involved

- **Next.js (App Router)** – Modern server + client component architecture  
- **Supabase (PostgreSQL)** – Relational database + real-time backend  
- **Clerk** – Authentication & user management  
- **OpenAI API** – AI-powered lessons and chat generation  
- **Shadcn UI** – Clean, accessible UI components  
- **TailwindCSS** – Utility-first CSS styling  
- **React Hook Form** – Fast, scalable form handling  
- **Zod** – Schema validation and type safety  
- **TypeScript** – Strong typing and maintainable code  
- **Vercel** – Hosting + serverless functions + deployment workflow  
