# URTEXT Blog Platform

A full-stack blogging platform built for readers and writers who appreciate clean, distraction-free content. The name _Urtext_ comes from music publishing: "original, unedited version of a score." The app is designed for any classical music enthusiasts who wish to be able to write music posts seamlessly (Music notation support to come!).

**Live Demo:** [blog-reader-lyart.vercel.app](https://blog-reader-lyart.vercel.app)

![Alt text](./public/preview-screenshot.png)

## Features

### Authentication

- Local registration with email/username and password
- OAuth login via GitHub and Google
- JWT-based session management
- Password reset via email (Resend)

### Posts

- Rich text editing with TinyMCE
- Draft/publish workflow
- Soft delete with trash/restore
- View tracking
- Like and save posts for later

### Social

- Follow/unfollow authors
- Subscribed feed (posts from authors you follow)
- Comments on posts

### User Profiles

- Public profile pages with post listings
- Separate tabs for published posts, drafts, and saved posts
- Follower/following counts

### Search & Discovery

- Full-text search across posts
- Sort by recent, popular, or most viewed
- Filter by author

## Tech Stack

### Backend (blog-api)

- **Runtime:** Node.js with Express
- **Database:** PostgreSQL with Prisma ORM
- **Authentication:** Passport.js (Local, GitHub, Google strategies) + JWT
- **Email:** Resend
- **Deployment:** Railway

### Frontend (blog-reader)

- **Framework:** React with React Router
- **Text Editor:** TinyMCE
- **Styling:** CSS
- **Deployment:** Vercel

### Admin Dashboard (blog-admin) (to be implemented soon)

- Separate interface for content management
- Post publishing controls
- Comment moderation
- Analytics

## Project Structure

This project uses a multi-repo architecture:

```
blog-project/
├── blog-api/           # Express + Prisma + PostgreSQL
│   ├── routes/
│   ├── middleware/
│   ├── prisma/
│   └── ...
├── blog-reader/        # React frontend
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── context/
│   │   └── ...
│   └── ...
├── blog-admin/         # React admin dashboard
│   └── ...
├── package.json        # Root scripts
└── README.md
```

## Local Development Instructions

### Prerequisites

- Node.js
- npm
- PostgreSQL database

### Setup

1. Clone the repository:

```bash
git clone https://github.com/lizzyjoo/blog-project
cd blog-project
```

2. Directory structure:

```
blog-project/
├── blog-api/        # Backend API
├── blog-reader/     # Public frontend
├── blog-admin/      # Admin dashboard
├── package.json     # Root scripts for running all apps
└── README.md
```

3. Set up environment variables:

**blog-api/.env**

```
DATABASE_URL=postgresql://user:password@localhost:5432/blog
JWT_SECRET=your-secret-key
FRONTEND_URL=http://localhost:5173
RESEND_API_KEY=your-resend-key
GITHUB_CLIENT_ID=your-github-client-id
GITHUB_CLIENT_SECRET=your-github-client-secret
GOOGLE_CLIENT_ID=your-google-client-id
GOOGLE_CLIENT_SECRET=your-google-client-secret
```

**blog-reader/.env**

```
VITE_API_URL=http://localhost:3000
```

4. Install dependencies for all apps:

```bash
npm run install:all
```

5. Set up the database:

```bash
cd ../blog-api
npx prisma migrate dev
npx prisma db seed  # Optional: seed with dummy data
```

6. Run everything concurrently:

```bash
npm run dev
```

This starts:

- API server at `http://localhost:3000`
- Blog reader at `http://localhost:5173`
- Admin dashboard at `http://localhost:5174`

## For future implementation

- [ ] Music notation support (for classical music content)
- [ ] Audio/video embeds for performance clips
- [ ] Score excerpt rendering
- [ ] Reading time estimates
- [ ] Post categories/tags
- [ ] Email notifications for new posts from followed authors

## Design Credits

| Element              | Source                                                                            |
| -------------------- | --------------------------------------------------------------------------------- |
| Blog UI inspiration  | [typography-themexpose](https://typography-themexpose.blogspot.com/)              |
| Add icon             | [Freepik](https://www.freepik.com/icon/add_15751421)                              |
| Profile post card    | [uiverse.io - quiet-bear-76](https://uiverse.io/Yaya12085/quiet-bear-76)          |
| 404 page emoji       | [Figma Community](https://www.figma.com/community/file/1280863093339672805)       |
| Login/signup form    | [Figma Community](https://www.figma.com/community/file/1401478816577651579)       |
| Settings menu button | [uiverse.io - popular-octopus-83](https://uiverse.io/portseif/popular-octopus-83) |
| Comment section      | [uiverse.io - quiet-turkey-90](https://uiverse.io/zanina-yassine/quiet-turkey-90) |
| About page quail     | [uiverse.io - lazy-quail-10](https://uiverse.io/AatreyuShau/lazy-quail-10)        |

## License

MIT

## Author

**Lizzy Joo** — [GitHub](https://github.com/lizzyjoo)
