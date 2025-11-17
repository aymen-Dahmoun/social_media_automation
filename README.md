🚀 Automated Social Media Content Pipeline (n8n Workflow)

This repository contains an n8n automation workflow that fully automates the process of:

Generating social media post ideas

Creating matching AI images and videos

Publishing content to Instagram, Facebook, and TikTok

Saving all generated content to Google Sheets for tracking

This workflow uses Google Gemini, Facebook Graph API, TikTok API, and Google Sheets.

📌 Features
✅ 1. AI-Generated Post Ideas

The workflow generates:

A short creative idea

An image prompt

A 50–80 word caption

10 hashtags
All formatted in JSON.

✅ 2. AI Image & Video Generation

Uses Google Gemini (Imagen & Veo models) to create:

An image for Instagram & Facebook

A TikTok-ready short video

✅ 3. Social Media Automation

Posts are automatically created and published on:

Instagram

Facebook Groups

TikTok

✅ 4. Google Sheets Caching

Every generated post is saved in a spreadsheet:

Idea

Caption

Hashtags

Image URL

Video URL

Timestamp

This helps you track previous posts and avoid duplicates.

🧩 Workflow Overview

Below is a simplified version of how the workflow operates:

Manual Trigger
Starts the workflow when you press “Execute Workflow”.

Generate Post Content
Calls Gemini → returns JSON with idea, caption, imagePrompt, hashtags.

Parse JSON Output
Extracts text and converts it into structured fields.

Generate Image
Uses Imagen 4.0 → returns imageUrl.

Generate Video
Uses Veo 3.0 → returns videoUrl.

Post to Social Media

Instagram upload + publish

Facebook post with caption & image

TikTok video upload

Structure Data
Prepares a clean JSON object for caching.

Save to Google Sheets
Stores all useful fields for later use.

🛠️ Technologies Used
Component	Used For
n8n	Automation engine
Google Gemini (PaLM)	Content, images, and video generation
Instagram Graph API	Image posting
Facebook Graph API	Facebook feed posting
TikTok API	Video uploads
Google Sheets	Post history caching
JavaScript Code Nodes	JSON parsing & data structuring
File Structure
/
├── social_media_autp_n8n.json
├── image.png

Setup Instructions
1. Import Workflow

Open n8n → Workflows

Click Import from File

Select workflow.json

2. Add Required Credentials

You must configure:

Service	Credential Type
Google Gemini	Google PaLM / Gemini API
Instagram / Facebook	HTTP Bearer Auth
TikTok API	HTTP Bearer Auth
Google Sheets	Google OAuth2
3. Replace Placeholder Values

Replace:

PLACEHOLDER_IG_USER_ID

PLACEHOLDER_GROUP_ID

with your actual Facebook/Instagram IDs.

▶️ Running the Workflow

Just click Execute Workflow and the pipeline will:

Generate post idea

Create images & videos

Publish them

Save everything to Google Sheets

Your content is fully automated 🎉
