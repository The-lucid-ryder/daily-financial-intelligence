# 📊 Daily Financial Intelligence - Automated Notion Updates

Automatically fetch worldwide financial news and investment insights every morning at 8 AM and post them to your Notion database.

## 🎯 What This Does

- **Searches** for major financial events worldwide
- **Analyzes** market movements and trends
- **Generates** aggressive growth investment opportunities
- **Creates** a new Notion page daily with comprehensive insights
- **Runs automatically** every morning at 8 AM via GitHub Actions (100% FREE!)

## 🚀 Quick Setup (5 Minutes)

### Step 1: Create a GitHub Account (if you don't have one)
1. Go to [github.com](https://github.com)
2. Click "Sign up" and follow the steps

### Step 2: Create Your Notion Integration

1. Go to [notion.so/my-integrations](https://www.notion.so/my-integrations)
2. Click **"+ New integration"**
3. Name it: "Daily Financial Updates"
4. Select your workspace
5. Click **"Submit"**
6. **Copy the "Internal Integration Token"** (starts with `secret_...`) - you'll need this!

### Step 3: Share Your Notion Database with the Integration

1. Open your **Daily Financial Intelligence** database in Notion (the one I created earlier)
2. Click the **"•••"** menu in the top right
3. Scroll down and click **"Add connections"**
4. Find and select **"Daily Financial Updates"** integration
5. Click **"Confirm"**

### Step 4: Get Your Notion Database ID

Your database URL looks like this:
```
https://www.notion.so/fb241507405d40acba310e3f5ad32311?v=...
                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
                      This is your DATABASE ID
```

**Copy the 32-character ID** from your database URL (between `.so/` and `?v=`)

### Step 5: Get a Free Serper API Key (Optional but Recommended)

1. Go to [serper.dev](https://serper.dev)
2. Sign up for free (Google sign-in available)
3. Free tier: **2,500 searches/month** (more than enough for daily updates!)
4. Copy your API key from the dashboard

### Step 6: Create Your GitHub Repository

1. Go to [github.com/new](https://github.com/new)
2. Repository name: `daily-financial-intelligence`
3. Choose **"Public"** (required for free GitHub Actions)
4. Click **"Create repository"**

### Step 7: Upload the Files

**Option A: Using GitHub Web Interface (Easiest)**

1. On your new repository page, click **"uploading an existing file"**
2. Download these files from me and upload them:
   - `daily_financial_update.py`
   - `requirements.txt`
   - `.github/workflows/daily-financial-update.yml`
3. Click **"Commit changes"**

**Option B: Using Git Command Line**

```bash
git clone https://github.com/YOUR_USERNAME/daily-financial-intelligence.git
cd daily-financial-intelligence

# Copy the files I created into this folder, then:
git add .
git commit -m "Initial setup"
git push
```

### Step 8: Add Your Secrets to GitHub

1. Go to your repository on GitHub
2. Click **"Settings"** tab
3. In the left sidebar, click **"Secrets and variables"** → **"Actions"**
4. Click **"New repository secret"**
5. Add these three secrets:

**Secret 1:**
- Name: `NOTION_API_KEY`
- Value: Your Notion integration token (from Step 2)

**Secret 2:**
- Name: `NOTION_DATABASE_ID`
- Value: Your database ID (from Step 4)

**Secret 3:**
- Name: `SERPER_API_KEY`
- Value: Your Serper API key (from Step 5)

### Step 9: Adjust the Timezone (Important!)

The default schedule is **8 AM EST (1 PM UTC)**. To change it:

1. Edit `.github/workflows/daily-financial-update.yml`
2. Find this line:
   ```yaml
   - cron: '0 13 * * *'  # 8 AM EST
   ```
3. Change it to your timezone:
   - **8 AM PST**: `'0 16 * * *'`
   - **8 AM CST**: `'0 14 * * *'`
   - **8 AM GMT**: `'0 8 * * *'`
   - **9 AM EST**: `'0 14 * * *'`

### Step 10: Test It Now!

1. Go to **"Actions"** tab in your GitHub repository
2. Click **"Daily Financial Intelligence Update"** workflow
3. Click **"Run workflow"** → **"Run workflow"**
4. Watch it run! (takes about 30 seconds)
5. Check your Notion database for the new page!

## ✅ You're Done!

Your automation will now run **every day at 8 AM automatically** and create a new page in your Notion database with:

- Major financial events worldwide
- Market analysis
- Aggressive growth investment opportunities
- Cash deployment strategy
- Risk factors and catalysts

## 🔧 Customization Options

### Change Update Frequency

Edit `.github/workflows/daily-financial-update.yml`:

```yaml
# Multiple times per day
- cron: '0 8,13,18 * * *'  # 8 AM, 1 PM, 6 PM

# Weekly on Monday
- cron: '0 13 * * 1'  # Monday at 8 AM EST

# Twice per week
- cron: '0 13 * * 1,4'  # Monday and Thursday
```

### Modify Investment Focus

Edit `daily_financial_update.py` and customize the `generate_investment_insights()` function to:
- Change from aggressive to conservative strategies
- Focus on specific sectors (tech, healthcare, energy)
- Add your own analysis logic

### Add More Data Sources

In `search_financial_news()`, you can add:
- **Alpha Vantage** (free stock data): [alphavantage.co](https://www.alphavantage.co)
- **NewsAPI** (free news): [newsapi.org](https://newsapi.org)
- **Yahoo Finance** (free via `yfinance` Python library)

## 🆓 Cost Breakdown

| Service | Free Tier | What We Use |
|---------|-----------|-------------|
| GitHub Actions | 2,000 minutes/month | ~1 minute/day = 30 min/month |
| Serper API | 2,500 searches/month | ~3 searches/day = 90/month |
| Notion API | Unlimited | Unlimited |
| **Total Cost** | **$0.00/month** | ✅ Well within limits |

## 🐛 Troubleshooting

### "Error 401: Unauthorized" in Notion
- Check that your `NOTION_API_KEY` secret is correct
- Make sure you shared the database with your integration (Step 3)

### "Error 404: Database not found"
- Verify your `NOTION_DATABASE_ID` is correct
- Ensure the database is shared with the integration

### Workflow Not Running
- Public repositories only for free GitHub Actions
- Check the cron schedule matches your timezone
- GitHub Actions can be delayed by up to 10 minutes during peak times

### No News Results
- Check your `SERPER_API_KEY` is valid
- Verify you haven't exceeded 2,500 searches/month
- The script will still run with fallback data if search fails

## 📝 Manual Trigger

You can always manually trigger an update:
1. Go to **Actions** tab on GitHub
2. Select **"Daily Financial Intelligence Update"**
3. Click **"Run workflow"**

## 🎓 Learn More

- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [Notion API Documentation](https://developers.notion.com)
- [Serper API Documentation](https://serper.dev/api-documentation)

## ⚠️ Disclaimer

This tool provides educational analysis based on publicly available market data. It is NOT personalized financial advice. Always conduct your own research and consider consulting a licensed financial advisor before making investment decisions. Markets are inherently risky.

---

**Created by: Claude (Anthropic)**
**License: MIT**
**Questions?** Open an issue on GitHub or modify the code to fit your needs!
