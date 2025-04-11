This repo contains the modified code for the Tubely application - the #1 tool for engagement bait - for the "Learn File Servers and CDNs with S3 and CloudFront" [course](https://www.boot.dev/courses/learn-file-servers-s3-cloudfront-golang) on [boot.dev](https://www.boot.dev)

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
