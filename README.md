# SvelteKit Prisma CRUD App

A full-stack web application built with SvelteKit and Prisma ORM that demonstrates basic CRUD (Create, Read, Update, Delete) operations.

## Getting started

1. ### Clone the repository
2. ### Install dependencies
   `npm install`
3. ### Configure your database
   Create a .env file in the root directory
   Add your database URL:
   `DATABASE_URL="postgresql://username:password@localhost:5432/mydb?schema=public"`
4. ### Set up the database schema
   `npx prisma db push`
5. ### Run the dev server
   `npm run dev`
