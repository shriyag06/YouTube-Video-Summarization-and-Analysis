# YouTube-Video-Summarization-and-Analysis using SLM

## Project Overview
This project allows users to summarize YouTube videos and playlists, extract metadata and transcripts, and analyze the textual content using natural language processing (NLP) embeddings. The system uses Alibaba-NLP/gte-large-en-v1.5 for embeddings and stores the data in a PostgreSQL database for further analysis.

## Features
Extract transcripts from YouTube videos or playlists using YouTubeTranscriptApi
Fetch video metadata (title, description, views, likes, etc.) using Pytube
Clean and preprocess video transcripts
Convert transcripts into embeddings using Alibaba-NLP/gte-large-en-v1.5
Store the metadata, transcripts, and embeddings in a PostgreSQL database
Analyze the transcripts to generate summaries and perform NLP-based analysis

## Tech Stack
Backend: Python, Flask
NLP Model: Alibaba-NLP/gte-large-en-v1.5
Data Storage: PostgreSQL
APIs: YouTubeTranscriptApi, Pytube
Language Models: SLM/LLM (Gamma 2: 2b)

## 1. Data Collection
YouTubeTranscriptApi: Used to extract transcripts (captions) from YouTube videos and playlists. This will give you the textual content (if available) for analysis.
You can pull transcripts automatically for videos with closed captions, making it easier to analyze speech content.
Pytube: Used to gather metadata from YouTube videos or playlists.
Metadata includes title, description, views, likes, duration, and other important information for each video.
Steps:

Fetch transcripts using YouTubeTranscriptApi for individual videos or an entire playlist.
Use Pytube to extract the metadata (such as video title, video ID, number of views, and other video statistics).
## 2. Data Cleaning
Once you have the transcript and metadata, the next step is to clean the data, which may involve:
Removing unnecessary punctuation, special characters, and stop words from the transcripts.
Ensuring consistency in the format of video metadata (e.g., numbers or strings).
Handling missing transcripts for videos that do not have closed captions available.
## 3. Embeddings
Alibaba-NLP/gte-large-en-v1.5: This model is used to convert the textual transcript data into embeddings—numerical representations of words, sentences, or paragraphs.
These embeddings will allow for sophisticated natural language processing tasks, like clustering similar video content or performing semantic analysis.
SLM / LLM (Gamma 2: 2b model): This is used to perform advanced analysis on the embeddings, possibly through a combination of summarization and other language understanding tasks.
Embedding Workflow:

Convert video transcripts into embeddings using Alibaba-NLP/gte-large-en-v1.5.
Perform operations like clustering or similarity searches using SLM/LLM models to find key themes across videos.
## 4. Data Storage
PostgreSQL: You will use this as your database to store both the cleaned transcripts and video metadata.
Each video will have its transcript, embedding representation, and metadata saved in a structured format in the PostgreSQL database.
This allows for efficient querying, retrieval, and analysis of the data.
Database Structure:

A table for video metadata (video ID, title, description, views, etc.).
A table for transcripts and their corresponding embeddings.
Relationships between videos and their respective transcripts and metadata.
## End-to-End Flow
Collect data (transcripts and metadata) from YouTube.
Clean the data (remove noise, format correctly).
Generate embeddings from the cleaned transcripts.
Store the cleaned data and embeddings in a PostgreSQL database for future analysis.
Analyze the data using embeddings and language models to generate insights, summarize content, or perform comparisons.
