# PDF to Speech Converter

The **PDF to Speech Converter** is a Python-based tool designed to read text from a PDF file and convert it into a high-quality spoken audio file. This project uses the `PyPDF2`, `gTTS`, and `pydub` libraries to extract text, synthesize speech, and enhance audio quality.

---

## Features

- Extracts text from PDF files.
- Converts the extracted text to an MP3 audio file.
- Improves the audio file's quality by increasing the sampling rate.

---

## Requirements

To use this project, you need the following:

- **Python 3.x**
- Python Libraries:
  - `gtts`
  - `PyPDF2`
  - `pydub`
- **ffmpeg**: Required for `pydub` to process audio files.

---

## Installation

Follow these steps to set up the project:

1. Install the required Python libraries:
   ```bash
   pip install gtts PyPDF2 pydub
    ````
   
<h1>Install ffmpeg:<h1>

    For Windows: Download and install from FFmpeg.org.
    For macOS: Use Homebrew:
