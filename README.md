# PDF to Speech Converter

This Python project aims to read text from a PDF file and convert it to a spoken audio file. It utilizes the `PyPDF2`, `gTTS`, and `pydub` libraries to extract text from a PDF and convert it to an MP3 file.

## Features

- Extract text from a PDF file
- Convert extracted text to an audio file
- Enhance the audio file's sampling rate

## Requirements

- Python 3.x
- `gtts` library
- `PyPDF2` library
- `pydub` library
- `ffmpeg` (required for `pydub` to work properly)

## Installation

You can install the required libraries using the following commands:

```bash
pip install gtts
pip install PyPDF2
pip install pydub
```
# -*- coding: utf-8 -*-
"""
Created on Fri Jul  8 12:11:16 2022

@author: Savage33
"""

from gtts import gTTS   
import PyPDF2
from pydub import AudioSegment

def Safir(text, output_path="high_quality_audio.mp3"):
    tts = gTTS(text=text, lang='tr')
    tts.save("good.mp3")
    audio = AudioSegment.from_file("good.mp3")
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
    pdf_path = r"C:\Users\Savage33\Downloads\istiklalmarşı.pdf"
    text = extract_text_from_pdf(pdf_path)
    print(text)
    Safir(text)


# PDF to Speech Converter

Bu Python projesi, bir PDF dosyasının metnini okuyarak sesli bir dosyaya dönüştürmeyi amaçlamaktadır. `PyPDF2`, `gTTS`, ve `pydub` kütüphanelerini kullanarak PDF dosyasındaki metni okur ve bunu bir MP3 dosyasına dönüştürür.

## Özellikler

- PDF dosyasından metin çıkarma
- Çıkarılan metni sesli dosyaya dönüştürme
- Çıktı ses dosyasının örnekleme oranını arttırma

## Gereksinimler

- Python 3.x
- `gtts` kütüphanesi
- `PyPDF2` kütüphanesi
- `pydub` kütüphanesi
- `ffmpeg` (Pydub'un çalışabilmesi için gereklidir)

## Kurulum

Aşağıdaki adımları izleyerek gerekli kütüphaneleri kurabilirsiniz:

```bash
pip install gtts
pip install PyPDF2
pip install pydub

