# MediaForge

A full-stack media transformation platform built with Next.js, Cloudinary, Clerk, Prisma, and PostgreSQL (Neon).

MediaForge allows users to securely authenticate, upload images and videos, apply media transformations, and manage their uploaded content through a web application.

## Features

* User authentication with Clerk
* Google OAuth authentication
* Image upload and transformation
* Customizable image dimensions
* Image download after transformation
* Video upload and compression
* Video metadata management
* Cloudinary-based media storage and transformation
* PostgreSQL database for video metadata
* Responsive web interface
* Protected application routes with Clerk middleware

## Tech Stack

* **Frontend:** Next.js, React, TypeScript
* **Authentication:** Clerk
* **Database:** PostgreSQL (Neon)
* **ORM:** Prisma
* **Media:** Cloudinary
* **UI:** Tailwind CSS, DaisyUI
* **HTTP Client:** Axios

## Application Flow

### Image Transformation

1. User signs in through Clerk.
2. User uploads an image.
3. MediaForge sends the image to Cloudinary.
4. Users can customize the image dimensions.
5. The transformed image can be downloaded.

### Video Upload

1. User signs in through Clerk.
2. User uploads a video.
3. The video is uploaded to Cloudinary.
4. Video metadata is stored in PostgreSQL through Prisma.
5. Uploaded videos are displayed in the application.

## Project Structure

```text
app/
├── (app)/
│   ├── home/
│   ├── social-share/
│   └── video-upload/
├── (auth)/
│   ├── sign-in/
│   └── sign-up/
└── api/
    ├── image-upload/
    ├── video-upload/
    └── videos/

components/
prisma/
public/
types/
```

## Getting Started

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd mediaforge
```

### 2. Install dependencies

```bash
npm install
```

### 3. Configure environment variables

Create a `.env` file for the database connection and a `.env.local` file for local application secrets.

Required variables include:

```env
DATABASE_URL=
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=
CLERK_SECRET_KEY=
NEXT_PUBLIC_CLOUDINARY_CLOUD_NAME=
CLOUDINARY_API_KEY=
CLOUDINARY_API_SECRET=
```

Never commit environment files or expose secret keys publicly.

### 4. Set up the database

```bash
npx prisma generate
npx prisma db push
```

### 5. Start the development server

```bash
npm run dev
```

Open:

```text
http://localhost:3000
```

## Production Build

To create a production build:

```bash
npm run build
```

To run the production build:

```bash
npm start
```

## Environment & Security

Environment variables containing credentials and API secrets are excluded from version control through `.gitignore`.

The application uses protected routes and Clerk authentication to restrict access to authenticated users.

## License

This project is intended as a personal portfolio project.
