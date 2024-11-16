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
   
<h1>Install ffmpeg:</h1>h1>

    For Windows: Download and install from FFmpeg.org.
    For macOS: Use Homebrew:
````bash
  brew install ffmpeg
````
    For Linux: Install via package manager (e.g., apt, yum).
<h1>Usage</h1>
Here’s an example of how the project works:
  
`````python
		from gtts import gTTS   
		import PyPDF2
		from pydub import AudioSegment

		def Safir(text, output_path="high_quality_audio.mp3"):
			tts = gTTS(text=text, lang='tr')
			tts.save("high_quality_audio.mp3")
			audio = AudioSegment.from_file("high_quality_audio.mp3")
			audio = audio.set_frame_rate(44100)  # Increase the sample rate
			audio.export(output_path, format="mp3")

		def extract_text_from_pdf(pdf_path):
			with open(pdf_path, "rb") as pdf_file:
				pdf_reader = PyPDF2.PdfReader(pdf_file)
				text = ""
				for page_num in range(len(pdf_reader.pages)):
					page = pdf_reader.pages[page_num]
					text += page.extract_text()
				return text

		if __name__ == "__main__":
			pdf_path = r"PDF File Path"
			text = extract_text_from_pdf(pdf_path)
			print(text)
			Safir(text)
``````

  <h1>Steps to Run</h1>
  
        Replace the pdf_path variable with the path to your PDF file.
        Run the script. The extracted text will be displayed, and the MP3 file will be saved as high_quality_audio.mp3.


