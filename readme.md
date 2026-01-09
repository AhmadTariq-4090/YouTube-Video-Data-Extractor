This n8n workflow provides an automated solution for extracting detailed information and full transcripts from YouTube videos using a simple web form.
📋 Overview

The YouTube Video Data Extractor allows users to input a YouTube URL via an n8n Form Trigger. The workflow then communicates with the Apify API to scrape the video's metadata and transcript, processes the data into a clean format, and stores the final results in an n8n Data Table for easy access and analysis.
🚀 Features

    User-Friendly Interface: Collects URLs via a built-in n8n form.

    Comprehensive Data Extraction: Captures Video Title, Channel Name, Publish Date, and the full Video Transcript.

    Automated Formatting: Uses custom JavaScript to merge transcript segments into a single, readable block of text.

    Persistent Storage: Automatically inserts all scraped data into a structured n8n Data Table.

🛠️ Workflow Nodes

    YouTube URL Form: A form trigger that captures the target YouTube URL.

    HTTP Request (Apify): Sends the URL to the starvibe/youtube-video-transcript actor on Apify to perform the scraping.

    Split Out: Breaks down the raw JSON response from the scraper.

    Aggregate: Recombines individual transcript lines into a unified list.

    Format Data (Code Node): A JavaScript node that cleans the metadata and joins the transcript text into a final string.

    Insert Row (Data Table): Saves the final record (URL, Title, Transcript, Channel, and Date) into the YoutubeScraperResults table.

🔧 Setup Instructions

    n8n Setup: Import the provided .json file into your n8n instance.

    Apify API Key:

        This workflow uses an Apify actor. You will need to replace the API token in the HTTP Request node with your own Apify API token.

        The current endpoint is configured for run-sync-get-dataset-items for immediate results.

    Data Table: Ensure you have an n8n Data Table named YoutubeScraperResults created, or update the Insert row node to point to your preferred storage (e.g., Google Sheets, Airtable, or SQL).