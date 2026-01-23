BrowserAct – Product Image to AI Video Automation (n8n)

Convert product images into professional AI-generated showcase videos using BrowserAct, n8n, and Google Veo.  
This workflow demonstrates how BrowserAct can be used as a production-grade data collection layer for downstream AI media generation.


🚀 Overview

This n8n workflow automates the entire pipeline from product data collection to short-form video generation:

- Collects structured product data using BrowserAct with real browser execution
- Parses product image URLs and metadata
- Iterates through each product in a controlled loop
- Downloads and converts images to Base64 format
- Submits video generation requests to an AI video generation API
- Polls generation status until completion
- Uploads both source images and generated videos to Google Drive
  
Each product is processed independently, making the workflow suitable for batch processing and scalable automation.


🧩 Why BrowserAct

BrowserAct is used as the core data collection layer in this workflow.

Instead of relying on fragile HTTP scraping or unofficial APIs, BrowserAct runs a real browser session to extract reliable, structured product data, including:

- Product titles
- Image URLs
- Page-level metadata
  
This ensures high data accuracy and makes the entire automation pipeline more stable and reproducible.


🔗 BrowserAct Workflow

This n8n workflow is designed to work together with a dedicated BrowserAct workflow responsible for product data collection.

BrowserAct Workflow Link:  
https://www.browseract.com/template/shopify-scraper-for-infinite-scroll-ecommerce-stores

The BrowserAct workflow provides the structured product output that is consumed by n8n for downstream image processing and AI video generation.


📦 Output (Google Drive)

For each product processed, the workflow uploads the following files to Google Drive:

- Product Name.jpg — original product image
- Product Name.mp4 — AI-generated showcase video
  
Files are automatically named based on the product title and grouped by execution.


🧠 Prompt Configuration

The workflow uses an editable text prompt to control the video generation style.

Default prompt used in the workflow:

Generate a professional 8-second e-commerce showcase video for this fashion or furniture item.  
The camera should perform a slow, elegant 360-degree pan in a bright studio to highlight texture and design details.

You can modify this prompt in the set_prompt node to customize:

- Video duration
- Camera movement
- Visual style
- Product category focus
  

🖼 Workflow Structure

The workflow is composed of the following logical stages:

1. Data Collection
Triggered manually and powered by BrowserAct to retrieve structured product data.
  
2. Image Preparation
Downloads each product image and converts it into a format suitable for AI generation.
  
3. Video Generation
Submits generation requests and waits asynchronously until videos are ready.
  
4. Drive Synchronization
Uploads both source images and generated videos to Google Drive.
  

🔧 How to Use

1. Import the workflow JSON into n8n.
2. Connect your BrowserAct account.
3. Configure Google Drive credentials.
4. Review and adjust the video prompt if needed.
5. Execute the workflow manually to verify output.
6. Enable scheduling or integrate into a larger automation pipeline.
  

🧠 Use Cases

- E-commerce product showcase videos
- Marketing asset generation at scale
- AI-powered content pipelines
- Browser-based data extraction + AI media workflows
  

✨ Notes

- The workflow is intentionally modular and easy to extend.
- You can replace the video generation API or storage provider if needed.
- BrowserAct can be reused for other product sources without changing the downstream logic.
  

Built with BrowserAct + n8n to demonstrate modern, browser-native automation for AI workflows.
