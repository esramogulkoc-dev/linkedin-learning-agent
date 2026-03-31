# LinkedIn Post Generator with Google Gemini API

An AI-powered tool that transforms weekly learning journal entries into professional LinkedIn posts using Google's Gemini API.

## Overview

This project automates the creation of LinkedIn posts for data analytics bootcamp students. It reads a weekly journal entry, extracts key topics and insights, and generates multiple post options in an enthusiastic, professional tone — ready to copy-paste or publish directly via the LinkedIn API.

## Features

- **AI-Powered Post Generation** — Uses Google Gemini (`gemini-2.5-flash-lite`) to craft polished LinkedIn posts from raw journal notes.
- **Multiple Post Options** — Generates 3 different post variations so you can pick the one that best fits your voice.
- **Topic & Insight Extraction** — Automatically identifies the main topics learned and key takeaways from your journal.
- **LinkedIn API Integration** — Optional direct publishing to LinkedIn via the UGC Posts API.
- **File Export** — Saves generated posts to a `.txt` file for later use.

## Project Structure

```
├── linkedin_post_generator.ipynb   # Main Jupyter notebook
├── generated_linkedin_posts.txt    # Output file with generated posts
├── .env                            # API keys (not tracked in git)
└── README.md
```

## Prerequisites

- Python 3.10+
- A Google Gemini API key
- (Optional) LinkedIn API credentials for direct posting

## Installation

1. Clone the repository:
   ```bash
   git clone <repo-url>
   cd linkedin-post-generator
   ```

2. Install dependencies:
   ```bash
   pip install google-genai python-dotenv requests
   ```

3. Create a `.env` file in the project root:
   ```env
   GOOGLE_API_KEY=your_google_api_key_here

   # Optional — only needed for direct LinkedIn posting
   LINKEDIN_ACCESS_TOKEN=your_linkedin_token
   LINKEDIN_PERSON_URN=urn:li:person:your_person_id
   ```

## Usage

### 1. Generate Posts (Simulation Mode)

Edit the `weekly_journal` variable in the notebook with your own notes, then run the cells. Example input:

```
This week in the Data Analytics Bootcamp, I explored pandas for data cleaning
and matplotlib for visualization.
My key insight: Cleaning messy datasets carefully makes analysis way more reliable.
```

The tool will output 3 LinkedIn post options with relevant hashtags, saved to `generated_linkedin_posts.txt`.

### 2. Publish to LinkedIn (Optional)

If you have LinkedIn API credentials configured in your `.env` file, the notebook includes a cell that posts the generated content directly to your LinkedIn profile.

> **Note:** The LinkedIn API requires an OAuth 2.0 access token with `w_member_social` permission. Tokens expire periodically and need to be refreshed.

## How It Works

1. **Input** — You provide a short weekly journal entry describing what you learned.
2. **Prompt Engineering** — A structured prompt instructs Gemini to extract topics and insights, then generate professional posts.
3. **Generation** — The Gemini API returns 3 post variations with hashtags.
4. **Output** — Posts are displayed in the notebook and saved to a text file (or published to LinkedIn).

## Example Output

```
This week in the Data Analytics Bootcamp has been all about building a strong
foundation! 📊 I've been diving deep into Pandas for data cleaning and
Matplotlib for visualization.

My biggest takeaway? The meticulous process of cleaning messy datasets is
absolutely crucial for reliable analysis.

#dataanalytics #bootcamp #learning #dataskills #pandas #matplotlib
```

## Environment Variables

| Variable | Required | Description |
|---|---|---|
| `GOOGLE_API_KEY` | Yes | Google Gemini API key |
| `LINKEDIN_ACCESS_TOKEN` | No | LinkedIn OAuth 2.0 token |
| `LINKEDIN_PERSON_URN` | No | Your LinkedIn person URN |

## License

This project is for educational purposes as part of a Data Analytics Bootcamp curriculum.
