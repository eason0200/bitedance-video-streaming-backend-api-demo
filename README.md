This repo contains the modified code for the Tubely application - a SaaS product that helps YouTubers manage their video assets. It allows users to upload, store, serve, add metadata to, and version their video files. It will also allow them to manage thumbnails, titles, and other video metadata.

## Project Goals
- Understand what "large" files are and how they differ from "small" structured data
- Build an app that uses AWS S3 and Go to store and serve assets
- Learn how to manage files on a "normal" (non-s3) filesystem based application
- Learn how to store and serve assets at scale using serverless solutions, like AWS S3
- Learn how to stream video and to keep data usage low and improve performance

## Quickstart

## 1. Install dependencies

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

## 2. Run the server

```bash
go run .
```

- You should see a new database file `tubely.db` created in the root directory.
- You should see a new `assets` directory created in the root directory, this is where the images will be stored.
- You should see a link in your console to open the local web page.
