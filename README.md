# NetEase Cloud Music Tracker

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
[![n8n Workflow](https://img.shields.io/badge/automated_with-n8n-29B6AF)](https://n8n.io)

Automated system that tracks NetEase Cloud Music listening history and generates daily reports published to GitHub Pages.

## 🌟 Features

- **5-minute sync**: Captures play records every 5 minutes
- **Daily reports**: Generates HTML reports at midnight
- **Zero infrastructure**: Fully hosted on GitHub Pages
- **Historical archive**: All raw data preserved in `/data` directory

## ⚙️ Workflow Architecture

```mermaid
graph LR
    A[5-min Cron] --> B[Fetch NetEase API]
    B --> C[Parse Data]
    C --> D[Push to GitHub]
    E[Daily Cron] --> F[Generate Report]
    F --> G[Publish HTML]
