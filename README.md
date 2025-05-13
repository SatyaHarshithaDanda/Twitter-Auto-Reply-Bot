# Twitter Auto-Reply Bot

This project is a simple **Twitter bot** built using Python and the **Tweepy** library. The bot monitors mentions on Twitter, and if a tweet contains the hashtag `#hello`, it automatically replies, likes, and retweets the tweet.

## Features

- Authenticates with the Twitter API using OAuth 1.0a.
- Checks for new mentions using `mentions_timeline`.
- Replies to tweets containing `#hello` with a friendly message.
- Likes and retweets those tweets.
- Maintains a record of the last seen tweet to avoid duplicate responses.
- Runs in a loop with a 15-second refresh interval.

## Requirements

- Python 3.x
- [Tweepy](https://www.tweepy.org/) (Install using `pip install tweepy`)
- Twitter Developer Account with API credentials

## Setup

1. **Clone the repository or copy the script.**

2. **Install dependencies:**
   ```bash
   pip install tweepy
   ```

3. **Set your Twitter API credentials** in `tweet_bot.py`:
   ```python
   consumer_key = 'Your API key goes here'
   consumer_secret = 'Your API secret key goes here'
   key = 'Your access_token goes here'
   secret = 'Your access_token_secret goes here'
   ```

4. **Create a file named `seen.txt` in the same directory** and add a starting tweet ID (e.g., `1`).

5. **Run the bot:**
   ```bash
   python tweet_bot.py
   ```

## How It Works

- The bot authenticates with Twitter using Tweepy.
- Every 15 seconds, it:
  - Fetches new mentions since the last seen tweet.
  - If the tweet contains `#hello`, it:
    - Replies with “All the best”
    - Likes the tweet
    - Retweets the tweet
  - Updates `seen.txt` to avoid reprocessing.

## Notes

- Be careful with rate limits and spam policies when interacting with Twitter's API.
- This bot is for educational/demo purposes. For production, you should implement error handling, logging, and scheduling improvements.
