# Automated Social Media Content Pipeline (n8n Workflow)

This repository provides a fully automated content creation and publishing pipeline built using **n8n**. The workflow generates post ideas, creates matching AI media, publishes content to multiple social platforms, and logs all generated data for future tracking.

## Overview

The workflow orchestrates a complete end-to-end automation process, integrating AI models, social media APIs, and Google Sheets. It is designed for creators, marketers, and automation engineers seeking a hands-free publishing system.

## Features

### 1. AI-Generated Post Ideas

The workflow uses Google Gemini to produce structured JSON containing:

* A short content idea
* An image prompt
* A 50–80 word caption
* Ten hashtags

### 2. AI Media Creation

Utilizing Google Gemini (Imagen and Veo models), the workflow automatically generates:

* An image suitable for Instagram and Facebook
* A short video suitable for TikTok

### 3. Automated Social Media Publishing

The workflow publishes generated content directly to:

* Instagram
* Facebook Groups
* TikTok

### 4. Google Sheets Caching

All generated content is saved to Google Sheets, including:

* Idea
* Caption
* Hashtags
* Image URL
* Video URL
* Timestamp

This ensures proper tracking and helps prevent duplicate posts.

## Workflow Summary

A simplified flow of how the automation operates:

1. Manual Trigger: Executes the workflow on demand.
2. Content Generation: Calls Gemini to produce structured JSON output.
3. JSON Parsing: Extracts fields and formats them for downstream nodes.
4. Image Generation: Calls Imagen to return an image URL.
5. Video Generation: Uses Veo to produce a video URL.
6. Social Media Posting: Uploads and publishes content across Instagram, Facebook, and TikTok.
7. Data Structuring: Prepares a final JSON object for storage.
8. Google Sheets Logging: Saves all important fields for later reference.

## Technologies Used

| Component             | Purpose                              |
| --------------------- | ------------------------------------ |
| n8n                   | Automation engine                    |
| Google Gemini (PaLM)  | Content, image, and video generation |
| Instagram Graph API   | Image publishing                     |
| Facebook Graph API    | Content posting                      |
| TikTok API            | Video uploads                        |
| Google Sheets API     | Post history caching                 |
| JavaScript Code Nodes | JSON parsing and data shaping        |

## File Structure

```
/
├── social_media_automation_n8n.json
├── image.png
```

## Setup Instructions

### 1. Import the Workflow

1. Open n8n and navigate to *Workflows*.
2. Select *Import from File*.
3. Choose the provided JSON file.

### 2. Configure Required Credentials

Set up the following credentials in n8n:

* Google Gemini (PaLM / Gemini API)
* Instagram and Facebook HTTP Bearer Authentication
* TikTok HTTP Bearer Authentication
* Google Sheets OAuth2

### 3. Replace Placeholder Values

Update the workflow with your actual identifiers:

* `PLACEHOLDER_IG_USER_ID`
* `PLACEHOLDER_GROUP_ID`

### 4. Running the Workflow

Once configured, click **Execute Workflow**. The system will:

* Generate a post idea
* Create an image and video
* Publish to all configured platforms
* Save all generated content to Google Sheets

This provides a complete and automated content production pipeline, requiring no manual intervention once active.
