# multipost7 — YouTube Channel 7 Automation

Automated video publishing, metadata generation via Gemini AI, comment response, and analytics reporting for **Marie Hutson** (`UCv-WTIg4kaB24NHFlZNsbcA`).

## Architecture & Workflows
- **Daily Upload (`daily-upload.yml`)**: Checks Google Drive inbox (`1Tdno6W9j6AOGPqfl4kGvcMFZuzvcXlJX`), analyzes video frames and audio using Gemini to infer topic and SEO metadata, uploads to YouTube, and moves completed videos to the `Uploaded` subfolder (`1v2xZDGdkHZzzWl4uhB7LZIq6tYaZZiXB`). Runs at 06:30, 12:30, and 18:30 PKT (01:30, 07:30, 13:30 UTC).
- **Comment Replies (`comment-replies.yml`)**: Fetches recent top comments and posts automated replies. Runs daily at 23:30 PKT (18:30 UTC).
- **Weekly Analytics (`weekly-analytics.yml`)**: Pulls view counts, watch time, and net subscribers via YouTube Analytics API. Runs Sundays at 00:30 PKT (19:30 UTC).

## Security & Isolation
- Full isolation for Channel 7 (dedicated GCP project `yt-multipost-channel7`, dedicated GitHub account `vdbdhxhhx-a11y`, isolated Drive folders).
- Zero plaintext secrets stored in code or repository.
