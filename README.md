This repo contains the code for the Tubely application - a SaaS product that helps YouTubers manage their video assets. It allows users to upload, store, serve, add metadata to, and version their video files. It will also allow them to manage thumbnails, titles, and other video metadata.

## Project Goals
- Understand what "large" files are and how they differ from "small" structured data
- Build an app that uses AWS S3 and Go to store and serve assets
- Learn how to manage files on a "normal" (non-s3) filesystem based application
- Learn how to store and serve assets at scale using serverless solutions, like AWS S3
- Learn how to stream video and to keep data usage low and improve performance

## Architecture
- Frontend: Javascript, HTML, CSS
- Backend: Golang
- 🔧 Backend Infrastructure Services

✅ Amazon S3
Category: Backend Infrastructure (Storage Layer)

Role: Persistent object storage for user-uploaded files, static assets (images, videos, PDFs), backups, and more.

Why: It handles durability, encryption, versioning, and secure file delivery.

✅ Amazon CloudFront
Category: Backend Infrastructure (Delivery Layer / CDN)

Role: Content Delivery Network that caches and serves static and dynamic content closer to users.

Why: It improves performance, reduces load on your origin (e.g., S3 or API), and can enforce security (OAI, signed URLs).

## Setup
## 1a. Clone the repository
   `https://github.com/eason0200/bitedance-video-streaming-backend-api-demo.git`
## 1b. Navigate to the project directory
   `cd bitedance-video-streaming-backend-api-demo`

## 2. Install dependencies

- [Go](https://golang.org/doc/install)
- `go mod download` to download all dependencies
- [FFMPEG](https://ffmpeg.org/download.html) - both `ffmpeg` and `ffprobe` are required to be in your `PATH`.

```bash
# linux
sudo apt update
sudo apt install ffmpeg

# windows: Chocolatey (easier for future updates)
# if you install FFMPEG using Chocolatey, it automatically adds both ffmpeg and ffprobe to your system PATH — no manual steps required.
choco install ffmpeg 

# mac
brew update
brew install ffmpeg
```

- [SQLite 3](https://www.sqlite.org/download.html) only required for you to manually inspect the database.

```bash
#windows : use VS Code third party SQL extension to open the database

# linux
sudo apt update
sudo apt install sqlite3

# mac
brew update
brew install sqlite3
```

## 3. Run the server

```bash
go run .
```

- You should see a new database file `tubely.db` created in the root directory.
- You should see a new `assets` directory created in the root directory, this is where the images will be stored.
- You should see a link in your console to open the local web page.

## 4. Open the local web page
- Sign up with a email address and password.

## Entities of the Web App
The two main entities in the app are videos and users. A user can have many videos, and a video belongs to a single user.

![image](https://github.com/user-attachments/assets/bf26e7dd-c5e6-4b8a-abc5-ddda5bf4e15a)


"Videos" have 3 things to worry about:

- Metadata: The title, description, and other information about the video
- Thumbnail: An image that represents the video
- Video: The actual video file
- 
Tubely allows users to create a "new draft" - which creates a new video record in the database containing metadata only. Thumbnails and video files are uploaded separately after the draft is created.
