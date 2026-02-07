# Example Inputs for automate_task

Use one of the following input formats to generate a complete automation script:

---

## Example 1: File Organization

```
Task: Organize my Downloads folder

Description:
Every day, my Downloads folder becomes a mess of random files. I need a script that:
1. Sorts files by type into subfolders (Documents, Images, Videos, Archives, Code, Other)
2. Moves files older than 30 days to an "Archive" folder
3. Deletes files older than 90 days
4. Runs automatically every night

File type mappings:
- Documents: .pdf, .doc, .docx, .txt, .xls, .xlsx, .ppt, .pptx
- Images: .jpg, .jpeg, .png, .gif, .svg, .webp
- Videos: .mp4, .mov, .avi, .mkv
- Archives: .zip, .rar, .7z, .tar, .gz
- Code: .py, .js, .ts, .html, .css, .json, .yaml, .md

Path: ~/Downloads
OS: macOS

Safety requirements:
- Don't delete anything without logging it first
- Create a log file of all actions taken
- Dry-run mode option to preview changes
```

---

## Example 2: Data Backup

```
Task: Backup important project files to cloud storage

Description:
I need to backup my active project folders to Google Drive daily. The script should:
1. Find all folders in ~/Projects that were modified in the last 24 hours
2. Create a compressed archive of each modified project
3. Upload to Google Drive using rclone
4. Keep only the last 7 backups per project
5. Send me a Slack notification when complete

Folders to backup:
- ~/Projects/client-work/
- ~/Projects/personal/
- ~/Documents/business/

Exclude patterns:
- node_modules/
- .git/
- __pycache__/
- .venv/
- *.log

Backup destination: gdrive:Backups/Projects/

Requirements:
- rclone is already configured
- Slack webhook URL: https://hooks.slack.com/services/XXX/YYY/ZZZ
```

---

## Example 3: Web Scraping / Data Collection

```
Task: Monitor competitor pricing and alert on changes

Description:
I need to track prices on 5 competitor websites daily and alert me when prices change. The script should:
1. Scrape the price from each product page
2. Compare to yesterday's prices (stored in a JSON file)
3. If price changed by more than 5%, send me an email alert
4. Update the price history file
5. Generate a weekly summary report

Competitor URLs and selectors:
- https://competitor1.com/product-x → CSS: .price-value
- https://competitor2.com/item/123 → CSS: #product-price
- https://competitor3.com/p/abc → CSS: span.current-price

Output:
- Daily JSON file: ~/data/prices/YYYY-MM-DD.json
- Weekly CSV report: ~/reports/price-report-WEEK.csv
- Email alerts to: me@company.com

Requirements:
- Handle rate limiting (1 request per 5 seconds)
- Handle page load failures gracefully
- Use rotating user agents
```

---

## Example 4: API Integration

```
Task: Sync contacts from HubSpot to Google Sheets daily

Description:
Every morning, I need an updated list of all contacts created in the last 7 days from HubSpot, formatted in a Google Sheet for my sales team. The script should:
1. Query HubSpot API for contacts created in last 7 days
2. Extract: Name, Email, Company, Phone, Create Date, Lead Source
3. Format and write to a specific Google Sheet
4. Clear old data and replace with fresh data
5. Send Slack message to #sales channel when complete

HubSpot API: I have an API key
Google Sheet ID: 1ABC123xyz...
Sheet name: "New Leads"

Columns needed:
| Full Name | Email | Company | Phone | Created | Source |

Requirements:
- Handle pagination (HubSpot limits to 100 per request)
- Handle API rate limits
- Log any errors to a file
- Run via cron at 7am daily
```

---

## Example 5: Media Processing

```
Task: Convert and optimize images for web

Description:
I have a folder of high-res images from our photographer. I need to process them for our website:
1. Resize to max 1920px width (maintain aspect ratio)
2. Create thumbnail versions (400px width)
3. Convert to WebP format (keep original as backup)
4. Compress to target 80% quality
5. Rename with slugified filenames (remove spaces, lowercase)
6. Generate an index.html with all thumbnails

Input folder: ~/Photography/Raw/
Output folder: ~/Photography/Web/
Thumbnail folder: ~/Photography/Web/thumbs/

Supported formats: .jpg, .jpeg, .png, .tiff
Skip if already processed (check output folder)

Requirements:
- Preserve EXIF data
- Don't overwrite existing files
- Generate processing log with before/after sizes
```

---

## Example 6: System Monitoring

```
Task: Monitor server health and alert on issues

Description:
I run a VPS that hosts my web applications. I need a script that:
1. Checks disk usage (alert if > 80%)
2. Checks memory usage (alert if > 90%)
3. Checks if key services are running (nginx, postgresql, redis)
4. Checks SSL certificate expiration (alert if < 14 days)
5. Checks website response time (alert if > 2 seconds)
6. Sends alerts via Telegram bot

Services to monitor:
- nginx
- postgresql
- redis-server
- my-app.service

Websites to check:
- https://myapp.com (expect 200)
- https://api.myapp.com/health (expect 200)

Alert destination:
- Telegram Bot Token: 123456:ABC-DEF...
- Chat ID: -987654321

Run every 5 minutes via cron.
Log all checks to /var/log/server-health.log
```

---

## Example 7: Content Automation

```
Task: Generate daily social media posts from RSS feeds

Description:
I want to automatically curate and schedule social media content from industry RSS feeds. The script should:
1. Fetch new articles from 5 RSS feeds
2. Filter for relevant keywords (AI, automation, productivity)
3. Generate a tweet-sized summary using a template
4. Add relevant hashtags
5. Save to a CSV for Buffer import (or post directly if possible)
6. Track which articles have been processed (avoid duplicates)

RSS Feeds:
- https://techcrunch.com/feed/
- https://www.theverge.com/rss/index.xml
- https://feeds.arstechnica.com/arstechnica/technology-lab

Keywords to match: AI, machine learning, automation, productivity, SaaS

Tweet template:
"📰 {title}\n\n{summary_50_words}\n\nRead more: {url}\n\n{hashtags}"

Output: ~/content/social-queue.csv
Columns: date, platform, content, url, status

Requirements:
- Limit to 3 posts per day
- Avoid duplicate URLs
- Handle feed parsing errors
```

---

## Quick Input Template

```
Task: [Brief title of what you want to automate]

Description:
[Detailed explanation of the task, step by step]

Inputs:
- [What data/files/sources does it work with?]

Outputs:
- [What should be created/modified/sent?]

Requirements:
- [Specific requirement 1]
- [Specific requirement 2]
- [Safety/error handling needs]

Environment:
- OS: [macOS / Linux / Windows]
- Existing tools: [What's already installed?]
- API keys available: [Any services you have access to?]

Schedule: [One-time / Daily / Weekly / On-demand]
```
