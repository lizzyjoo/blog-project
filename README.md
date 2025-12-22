# Blog Project

A full-stack blogging platform consisting of three separate applications:

- REST API backend
- Public blog reader
- Admin dashboard

This repository serves as the **development orchestrator**, allowing all services to be run simultaneously with a single command.

## Repositories

- **blog-api** – Backend API (Node.js, Express, database)
- **blog-reader** – Public-facing blog frontend
- **blog-admin** – Admin dashboard for managing posts

Each repository is developed independently but designed to work together.

## Local Development

### Prerequisites

- Node.js
- npm

### Setup

Clone all repositories into the same parent directory:

```bash
git clone https://github.com/lizzyjoo/blog-project
git clone https://github.com/lizzyjoo/blog-api
git clone https://github.com/lizzyjoo/blog-reader
git clone https://github.com/lizzyjoo/blog-admin
```

Your directory structure should looklike this:

```bash
parent-directory/
├── blog-project/
├── blog-api/
├── blog-reader/
└── blog-admin/
```

Install dependencies for all apps:

```bash
npm run install:all
```

To run everything concurrently:

```bash
npm run dev
```

This will start the API server, Blog reader frontend, and the Admin dashboard.
