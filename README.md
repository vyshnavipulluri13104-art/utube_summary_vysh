# YouTube Video Summarizer

## Overview

YouTube Video Summarizer is an application that automatically transcribes and summarizes YouTube videos using speech recognition and Large Language Models (LLMs).

The application takes a YouTube video URL, extracts its audio, converts speech into text using Whisper, and generates concise summaries using a locally running LLaMA 2 model integrated through Haystack.

It provides an end-to-end pipeline for processing long-form video content while preserving important information and key insights.

## Key Features

- **Audio Transcription:** Uses OpenAI Whisper to convert video audio into text.
- **AI-Powered Summarization:** Generates concise summaries using a locally hosted LLaMA 2 model.
- **Long-Form Video Processing:** Implements text chunking to handle transcripts exceeding the model's context window.
- **Local LLM Execution:** Runs a quantized GGUF version of LLaMA 2 locally.
- **Interactive Interface:** Provides a Streamlit interface for submitting video links, viewing transcriptions, and reading generated summaries.

## Tech Stack

- **Frontend:** Streamlit
- **Speech Recognition:** Whisper
- **Language Model:** LLaMA 2
- **LLM Integration:** Haystack
- **Model Format:** GGUF (Quantized)
- **Audio Processing:** yt-dlp and FFmpeg
- **Programming Language:** Python

## Project Highlights

### 1. End-to-End Video Summarization Pipeline

- Architected an end-to-end pipeline integrating Whisper, LLaMA 2, and Haystack to transcribe long-form videos and generate summaries.
- Achieved an average **65% text compression** while preserving key insights.
- Automated the workflow from YouTube video input and audio extraction to transcription and AI-generated summaries.

### 2. Long-Form Transcript Processing

- Implemented text chunking to divide lengthy transcripts into manageable segments.
- Processed transcript chunks within the context window of a locally run, quantized (GGUF) LLaMA 2 model.
- Enabled the processing and summarization of long-form video inputs.

### 3. Interactive Streamlit Interface

- Built a Streamlit interface for linking YouTube videos, viewing generated transcriptions, and reading structured summaries.
- Integrated the transcription and summarization pipeline into an interactive application.

## System Architecture

The application follows a sequential processing pipeline:

1. **YouTube URL Input:** The user provides a YouTube video link.
2. **Audio Extraction:** yt-dlp downloads the video's audio.
3. **Audio Conversion:** FFmpeg converts the extracted audio into MP3 format.
4. **Speech Transcription:** Whisper converts the audio into text.
5. **Text Chunking:** Long transcripts are divided into smaller chunks to fit within the LLaMA 2 context window.
6. **LLM Processing:** Haystack integrates the prompt-processing pipeline with the locally running LLaMA 2 model.
7. **Summary Generation:** LLaMA 2 generates concise summaries of the transcript.
8. **Output Display:** Streamlit displays the video, transcription, and generated summary.

## Setup Instructions

### 1. Clone the Repository and Install Dependencies

Clone the repository and navigate into the project directory.

Create and activate a virtual environment (recommended):

```bash
python -m venv venv
```

Activate the environment:

**Windows:**

```bash
venv\Scripts\activate
```

**macOS/Linux:**

```bash
source venv/bin/activate
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

### 2. Download the LLaMA 2 Model

Download the quantized LLaMA 2 model using:

```bash
wget https://huggingface.co/TheBloke/Llama-2-7B-32K-Instruct-GGUF/resolve/main/llama-2-7b-32k-instruct.Q4_K_M.gguf
```

Make sure to download the model into the same directory as `yt_summary.py`.

### 3. Start the Application

Run the following command:

```bash
streamlit run yt_summary.py
```

Once the application starts, open the Streamlit URL displayed in the terminal.

Processing may take some time depending on the video duration and available system resources.

---

**YouTube Video Summarizer — Transcribe. Understand. Summarize.**
