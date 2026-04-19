# trends-agent-investment

Live alternative data for AI investing and equity research agents. One
MCP connection to news sentiment, Reddit subscriber growth, Wikipedia
page views, Google Search, Amazon, Steam, App Store, and more. Free
tier, no scraping.

> Live trend data for AI agents. One connection. Every platform.
> Powered by [trendsmcp.ai](https://trendsmcp.ai)

## Why this exists

AI investing agents need real signals, not opinions. Trends MCP gives
your agent attention proxies (Google Search, Wikipedia, news volume),
sentiment proxies (news sentiment, Reddit), and demand proxies (Amazon,
App Store, Steam) through one MCP server, with one API key and a
normalized 0 to 100 scale.

These are alternative signals, not financial advice. Combine with
fundamentals and your own research process.

## Get your free API key

1. Go to [trendsmcp.ai](https://trendsmcp.ai)
2. Enter your email, key sent instantly
3. 100 free requests per month, no credit card

[Get your free key](https://trendsmcp.ai)

## Connect any AI tool in 30 seconds

Pick the client your research workflow lives in. Full snippets are at
[trendsmcp.ai/docs](https://trendsmcp.ai/docs).

- **Claude Desktop / Claude.ai / Claude mobile.** Add a custom
  connector with name `Trends MCP` and server URL
  `https://www.trendsmcp.ai/mcp`.
- **ChatGPT.** Add as a custom connector on a plan that supports them,
  or call the REST API from a Custom GPT Action.
- **Cursor / Windsurf / VS Code Copilot.** MCP config in the IDE for
  research-plus-code workflows in notebooks.
- **Direct API from Python.** Wire it into your existing quant or
  notebook stack.

```python
import requests

res = requests.post(
    "https://api.trendsmcp.ai/api",
    headers={"Authorization": "Bearer YOUR_API_KEY"},
    json={"source": "news sentiment", "keyword": "Tesla"},
).json()
print(res)
```

## What you can ask an investing agent

- "Using TrendsMCP, show me 6 month news sentiment for `Meta` and flag every drop greater than 20 percent week over week."
- "Via TrendsMCP, compare Reddit subscriber growth for `wallstreetbets` and `stocks` over 1 year."
- "Using TrendsMCP, get Wikipedia page views for `Bitcoin` weekly over 5 years."
- "Via TrendsMCP, show me Google Search trend for `recession` over 5 years."
- "Using TrendsMCP, list the App Store Top Free apps right now."
- "Via TrendsMCP, what is the Amazon search trend for `home solar` over 12 months?"
- "Using TrendsMCP, fetch Steam concurrent players for the top 10 games this month."

## Investing use cases this unlocks

- **Alternative data for AI quant agents.** Use attention, sentiment,
  and demand proxies as features alongside price and fundamentals.
- **Retail investor sentiment tracking.** Combine Reddit subscriber
  growth with news sentiment to detect rising or fading hype cycles.
- **Catalyst monitoring.** Watch Google News volume and news sentiment
  to flag idiosyncratic events on your watchlist.
- **Consumer demand reads.** Amazon, App Store, and Steam data give
  early reads on consumer products, app companies, and game studios.
- **Theme rotation research.** Compare Google Search interest across
  themes (AI, weight loss drugs, EVs, semis) on a normalized scale.
- **Investment memos.** Have an AI research agent pull data, score
  signals, and draft a memo in one chat.

## Three tools your AI gets

- `get_trends`, historical time series for any keyword on any source
  (5 years weekly, 30 days daily where supported).
- `get_growth`, percentage change over any period (7D, 1M, 3M, 6M, 1Y,
  YTD, custom dates).
- `get_top_trends`, what is trending right now across live platform feeds.

## All data sources in one connection

One API key gives your investing agent every keyword source and every
live feed below.

### Keyword sources (Get Trends and Get Growth)

| source | What it measures | Keyword format |
| --- | --- | --- |
| `google search` | Google search volume | Any keyword or phrase |
| `google images` | Google image search volume | Any keyword or phrase |
| `google news` | Google News search volume | Any keyword or phrase |
| `google shopping` | Google Shopping search volume | Any keyword or phrase |
| `youtube` | YouTube search volume | Any keyword or phrase |
| `tiktok` | TikTok hashtag volume | Hashtag or topic |
| `reddit` | Subreddit subscribers | Subreddit name only, no `r/` prefix |
| `amazon` | Amazon product search volume | Product name or category |
| `wikipedia` | Wikipedia page views | Article title or topic |
| `news volume` | News article mention volume | Any keyword or phrase |
| `news sentiment` | News sentiment score (positive / negative) | Any keyword or phrase |
| `app downloads` | Mobile app download estimates (Android) | Package id or app identifier |
| `npm` | npm package weekly downloads | Exact package name e.g. react |
| `steam` | Steam concurrent players (monthly) | Game display name e.g. Elden Ring |

All values are normalized to a 0 to 100 scale where the pipeline supports
it, so you can compare different sources directly.

### Live leaderboards (Get Top Trends)

Google Trends, Google News Top News, TikTok Trending Hashtags, YouTube
Trending, X (Twitter) Trending, Reddit Hot Posts, Reddit World News,
Wikipedia Trending, Amazon Best Sellers Top Rated, Amazon Best Sellers by
Category, App Store Top Free, App Store Top Paid, Google Play, Top
Websites, Spotify Top Podcasts, Steam Most Played, GitHub Trending Repos,
IMDb MOVIEmeter, Trending Books.

The source list evolves over time. Authoritative reference at
[trendsmcp.ai/docs](https://trendsmcp.ai/docs).

## Pricing

Free forever for 100 requests per month. Paid plans available. See
[trendsmcp.ai/pricing](https://trendsmcp.ai/pricing).

## Resources

- [Get a free API key](https://trendsmcp.ai)
- [Documentation and full reference](https://trendsmcp.ai/docs)
- [Pricing](https://trendsmcp.ai/pricing)
- [All TrendsMCP repositories](https://github.com/trendsmcp)

## Disclaimer

Trends MCP provides alternative data signals. It is not investment
advice. Past patterns do not predict future returns. Combine with your
own research and risk management.

## Security

Never commit your API key to a public repository. Use environment
variables or your OS secret store. Keys can be rotated at any time from
your TrendsMCP dashboard. The `YOUR_API_KEY` placeholder above is a
literal string to replace with your own key after you copy the snippet
locally.

## License

MIT. See [LICENSE](./LICENSE).
