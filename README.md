# YouTube Comments Scraper + Replies, Shorts · No API Key · $1/1K

Get the comments and replies of any YouTube video or Short: text, author and channel ID, likes, reply count, creator heart, and when it was posted. Top comments or newest first. Paste one video or hundreds.

**[Run it on Apify](https://apify.com/pomlabs/youtube-comments-scraper?utm_source=github&utm_medium=readme&utm_campaign=youtube-comments-scraper)**: no install, no login, free credit on a new Apify account.

## What you get

- **Comment text** with author handle, channel ID and avatar
- **Engagement**: likes (numbers, not "4.8M" text) and reply count
- **Replies** linked to their parent (`isReply`, `parentCommentId`), with a cap per comment so you get breadth, not one long thread
- **Creator heart** flag
- **Time**: the text YouTube shows ("6 years ago") and an approximate ISO date computed from it
- **Sort** like the YouTube comment section: top comments or newest first

## Pricing

**No API key, no daily quota. You pay only for comments delivered: $0.001 per comment.** Videos with comments turned off and invalid links are listed with the reason and never charged.

That is the free-plan price; Apify paid plans (Bronze, Silver, Gold) pay less per item.

## Call it by API

```bash
curl -X POST "https://api.apify.com/v2/acts/pomlabs~youtube-comments-scraper/run-sync-get-dataset-items?token=YOUR_APIFY_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"videos": ["https://www.youtube.com/watch?v=dQw4w9WgXcQ"]}'
```

Python:

```python
from apify_client import ApifyClient

client = ApifyClient("YOUR_APIFY_TOKEN")
run = client.actor("pomlabs/youtube-comments-scraper").call(run_input={"videos": ["https://www.youtube.com/watch?v=dQw4w9WgXcQ"]})
for item in client.dataset(run["defaultDatasetId"]).iterate_items():
    print(item)
```

## Use it from Claude, Cursor or any MCP client

```bash
claude mcp add youtube-comments "https://mcp.apify.com?tools=pomlabs/youtube-comments-scraper" -t http
```

## Ready-made examples

- [Export YouTube comments to Excel or CSV](https://apify.com/pomlabs/youtube-comments-scraper/examples/export-youtube-comments-csv)
- [Get YouTube Shorts comments with replies](https://apify.com/pomlabs/youtube-comments-scraper/examples/youtube-shorts-comments-replies)
- [Newest YouTube comments for sentiment analysis](https://apify.com/pomlabs/youtube-comments-scraper/examples/newest-youtube-comments-sentiment)

## More Actors by Pom Labs

- [LinkedIn Profile Scraper (No Cookies) + Similar Profiles](https://apify.com/pomlabs/linkedin-profile-scraper?utm_source=github&utm_medium=readme&utm_campaign=youtube-comments-scraper)
- [Instagram Profile Scraper: Exact Followers, Reels Views](https://apify.com/pomlabs/instagram-profile-data?utm_source=github&utm_medium=readme&utm_campaign=youtube-comments-scraper)
- [YouTube Transcript Scraper: Translate, No Login · $3/1K](https://apify.com/pomlabs/youtube-transcript-scraper?utm_source=github&utm_medium=readme&utm_campaign=youtube-comments-scraper)
- [Video Downloader: TikTok No Watermark, Instagram, YouTube, X](https://apify.com/pomlabs/video-downloader?utm_source=github&utm_medium=readme&utm_campaign=youtube-comments-scraper)
- [LinkedIn Company Scraper (No Cookies): Posts, Similar Companies](https://apify.com/pomlabs/linkedin-company-scraper?utm_source=github&utm_medium=readme&utm_campaign=youtube-comments-scraper)
- [Threads Scraper: Keyword Search, Posts & Profiles · No Login](https://apify.com/pomlabs/threads-scraper?utm_source=github&utm_medium=readme&utm_campaign=youtube-comments-scraper)
- [AliExpress Scraper: Exact Units Sold, Prices, Search · $1/1K](https://apify.com/pomlabs/aliexpress-scraper?utm_source=github&utm_medium=readme&utm_campaign=youtube-comments-scraper)
- [Instagram Transcript Scraper: Reels, TikTok, Facebook, Hook](https://apify.com/pomlabs/social-video-transcript?utm_source=github&utm_medium=readme&utm_campaign=youtube-comments-scraper)
- [Reddit Scraper: Deleted & Removed, Mods, Hidden Profiles](https://apify.com/pomlabs/reddit-posts-comments-scraper?utm_source=github&utm_medium=readme&utm_campaign=youtube-comments-scraper)

Full documentation, input fields and output format: [YouTube Comments Scraper + Replies, Shorts · No API Key · $1/1K on Apify](https://apify.com/pomlabs/youtube-comments-scraper?utm_source=github&utm_medium=readme&utm_campaign=youtube-comments-scraper).
