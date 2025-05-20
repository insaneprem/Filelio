# Filelio

Filelio is a modern, full-stack file storage and management application. It features secure authentication, cloud file uploads, folder organization, starring, trash, and a beautiful, responsive UI. Built with Next.js, Clerk, Neon PostgreSQL, Drizzle ORM, ImageKit, and HeroUI.

---

## 🚀 Features

- **User Authentication**: Secure sign-up/sign-in with Clerk
- **File Uploads**: Upload and manage images (and PDFs) with ImageKit
- **Folders & Organization**: Create folders, move files, and organize your storage
- **Star & Trash**: Star important files, move files to trash, empty trash
- **Responsive UI**: Built with HeroUI and Tailwind CSS for a seamless experience
- **Cloud Database**: Uses Neon PostgreSQL with Drizzle ORM
- **RESTful API**: Endpoints for file and folder management
- **Production Ready**: Easily deploy to Vercel, Render, or your favorite platform

---

## 🛠️ Tech Stack

- **Frontend**: Next.js (App Router), React, TypeScript, Tailwind CSS, HeroUI
- **Authentication**: [Clerk](https://clerk.com/)
- **Database**: [Neon PostgreSQL](https://neon.tech/)
- **ORM**: [Drizzle ORM](https://orm.drizzle.team/)
- **File Storage**: [ImageKit](https://imagekit.io/)
- **Other**: Axios, React Hook Form, Zod, Lucide Icons

---

## 📁 Directory Structure

```
Filelio/
  app/                # Next.js app directory (pages, API routes)
    api/              # REST API endpoints (files, folders, upload, etc.)
    dashboard/        # User dashboard page
    sign-in/          # Sign-in page
    sign-up/          # Sign-up page
    ...
  components/         # React UI components (Navbar, FileList, FileUploadForm, etc.)
  lib/                # Database and utility functions
  drizzle/            # Drizzle ORM migrations and schema
  public/             # Static assets
  styles/             # Global styles (Tailwind)
  config/             # App and font config
  schemas/            # Zod validation schemas
  types/              # TypeScript types
  ...
```

---

## ⚙️ Getting Started

### Prerequisites

- Node.js 18+ and npm
- Clerk account (for authentication)
- Neon PostgreSQL database (or compatible Postgres)
- ImageKit account (for file storage)

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/filelio.git
   cd filelio
   ```

2. **Install dependencies:**
   ```bash
   npm install
   # or
   yarn install
   # or
   pnpm install
   ```

3. **Set up environment variables:**

   Create a `.env.local` file in the root directory with the following:

   ```env
   # Clerk Authentication
   NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
   CLERK_SECRET_KEY=your_clerk_secret_key

   # ImageKit
   NEXT_PUBLIC_IMAGEKIT_PUBLIC_KEY=your_imagekit_public_key
   IMAGEKIT_PRIVATE_KEY=your_imagekit_private_key
   NEXT_PUBLIC_IMAGEKIT_URL_ENDPOINT=your_imagekit_url_endpoint

   # Clerk URLs
   NEXT_PUBLIC_CLERK_SIGN_IN_URL=/sign-in
   NEXT_PUBLIC_CLERK_SIGN_UP_URL=/sign-up
   NEXT_PUBLIC_CLERK_AFTER_SIGN_IN_URL=/dashboard
   NEXT_PUBLIC_CLERK_AFTER_SIGN_UP_URL=/dashboard

   # App URLs
   NEXT_PUBLIC_APP_URL=http://localhost:3000

   # Database - Neon PostgreSQL
   DATABASE_URL=your_neon_database_url
   ```

4. **Set up your accounts and get API keys:**
   - [Clerk](https://clerk.com/)
   - [Neon](https://neon.tech/)
   - [ImageKit](https://imagekit.io/)

---

## 🗄️ Database & Migrations

- **Drizzle ORM** is used for schema and migrations.
- To run migrations:
  ```bash
  npm run db:generate  # Generate migrations
  npm run db:push      # Push schema to database
  ```
- Database schema is defined in `lib/db/schema.ts`.

---

## 🧩 Main Components

- `Navbar.tsx` — Top navigation bar
- `DashboardContent.tsx` — Main dashboard logic
- `FileList.tsx` — File/folder listing
- `FileUploadForm.tsx` — File upload UI
- `SignInForm.tsx` / `SignUpForm.tsx` — Auth forms
- `FolderNavigation.tsx` — Folder tree navigation
- `FileActions.tsx` / `FileActionButtons.tsx` — File management actions

---

## 📡 API Endpoints

### File Management

- `GET /api/files?userId=...&parentId=...` — List files/folders (optionally by parent folder)
- `POST /api/files/upload` — Upload a file (multipart/form-data)
- `PATCH /api/files/[fileId]/star` — Star/unstar a file
- `PATCH /api/files/[fileId]/trash` — Move file to trash or restore
- `DELETE /api/files/[fileId]/delete` — Permanently delete a file
- `DELETE /api/files/empty-trash` — Empty the trash for the current user

### Folder Management

- `POST /api/folders/create` — Create a new folder

### ImageKit Auth

- `GET /api/imagekit-auth` — Get ImageKit authentication parameters

---

## 🖥️ Running Locally

```bash
npm run dev
# or
yarn dev
```
Visit [http://localhost:3000](http://localhost:3000)

---

## 🚀 Deployment

### Deploy to Vercel

1. Push your code to GitHub.
2. Go to [Vercel](https://vercel.com/), import your repo, and set environment variables.
3. Deploy!

### Deploy to Render

1. Push your code to GitHub.
2. Go to [Render](https://render.com/), create a new Web Service, and connect your repo.
3. Set build command: `npm install && npm run build`
4. Set start command: `npm start`
5. Add environment variables.
6. Deploy!

---

## 📝 Scripts

- `npm run dev` — Start development server
- `npm run build` — Build for production
- `npm start` — Start production server
- `npm run lint` — Lint code with ESLint
- `npm run db:generate` — Generate Drizzle migrations
- `npm run db:push` — Push schema to database
- `npm run db:studio` — Open Drizzle Studio
- `npm run db:migrate` — Run custom migration script

---

## 🤝 Contributing

Contributions are welcome! Please open issues or pull requests for improvements or bug fixes.

---

## 📄 License

This project is licensed under the MIT License.

---

## 🙏 Acknowledgements

- [Next.js](https://nextjs.org/)
- [Clerk](https://clerk.com/)
- [Neon](https://neon.tech/)
- [Drizzle ORM](https://orm.drizzle.team/)
- [ImageKit](https://imagekit.io/)
- [HeroUI](https://heroui.dev/)

---

**Enjoy using Filelio! If you have questions or need help, open an issue or reach out.** 