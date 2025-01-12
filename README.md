```markdown
# Whisper Video Subtitle Generator

This project utilizes the powerful [Whisper](https://github.com/openai/whisper) model from Hugging Face to generate subtitles for video files and seamlessly embed them into the video. Built with Flask for the web interface and MoviePy for video processing, this application streamlines the process of adding subtitles to your videos.

The core functionality involves transcribing the audio track of a video into text, converting this text into the standard `.srt` subtitle format, and finally overlaying these subtitles onto the video.

## Features

* **Audio Extraction:** Extracts audio from uploaded video files.
* **Whisper Transcription:** Generates accurate subtitles from the extracted audio using the Hugging Face Transformers library and the Whisper model.
* **Subtitle Embedding:** Embeds the generated subtitles directly into the video.
* **Simple Web Interface:** Offers an intuitive Flask web application for uploading videos and downloading the subtitled output.

## Tech Stack

* **Python:**  Primary programming language.
* **Flask:**  Web framework for building the user interface.
* **Transformers:**  Provides access to the Whisper model.
* **MoviePy:**  Python library for video editing and processing.
* **ffmpeg-python:**  Python interface for FFmpeg.
* **pysrt:**  Python library for manipulating SRT subtitle files.
* **torch:**  Required for running the Whisper model.
* **FFmpeg:**  Essential for audio extraction and video processing.
* **ImageMagick:**  Used by MoviePy for subtitle overlay.

## Installation Steps

Follow these steps to get the application up and running on your local machine.

**Step 1: Clone the Repository**

```bash
git clone https://github.com/your-username/whisper-video-subtitle-generator.git
cd whisper-video-subtitle-generator
```

**Step 2: Create a Virtual Environment (Optional but Recommended)**

```bash
python -m venv venv
source venv/bin/activate  # For Linux/macOS
venv\Scripts\activate  # For Windows
```

**Step 3: Install Dependencies**

```bash
pip install -r requirements.txt
```

**Dependencies:**

```
Flask
Transformers
MoviePy
ffmpeg-python
torch
pysrt
```

**Note:** FFmpeg and ImageMagick need to be installed separately as described in the following steps.

**Step 4: Install ImageMagick**

ImageMagick is crucial for the subtitle overlay process within MoviePy.

* **Download and install ImageMagick** from the official website: [https://imagemagick.org/script/download.php](https://imagemagick.org/script/download.php)
* **Ensure ImageMagick is added to your system's PATH** during the installation process. This allows the application to find the necessary executables.

**Step 5: Set Up FFMPEG**

FFmpeg is used for extracting audio from the uploaded video files.

* **Download FFmpeg** from the official website: [https://ffmpeg.org/download.html](https://ffmpeg.org/download.html)
* **Add the `bin` directory of your FFmpeg installation to your system's PATH** environment variable. This ensures that the `ffmpeg` command is accessible from your terminal.

**Step 6: Run the Flask App**

Navigate to the project directory in your terminal and execute the following command:

```bash
python app.py
```

This will start the Flask development server. You can access the application in your web browser at `http://127.0.0.1:5000/`.

**Step 7: Upload and Process a Video**

1. Open the application in your web browser.
2. You will find an upload form where you can select a video file from your computer.
3. Click the "Upload" button.
4. The application will then:
    * Extract the audio from the uploaded video.
    * Generate subtitles using the Whisper model.
    * Embed the generated subtitles into the video.
5. Once the process is complete, a download link for the subtitled video will be available on the page.

## File Structure

```
whisper-video-subtitle-generator/
├── app.py                # Main Flask application file
├── uploads/              # Directory to store uploaded videos
├── output/               # Directory to store output videos with subtitles
├── requirements.txt      # List of Python dependencies
├── templates/
│   └── index.html        # HTML template for the Flask app
└── README.md             # This README file
```

## Known Issues and Considerations

* **FFmpeg and ImageMagick on PATH:** Ensure that both FFmpeg and ImageMagick are correctly installed and their respective executable directories are added to your system's PATH environment variable. This is crucial for the video processing functionalities.
* **Processing Time:** Generating subtitles, especially for large video files, can take a significant amount of time depending on your system's resources and the video length.
* **Whisper Model Performance:** The accuracy of the generated subtitles depends on the audio quality and clarity of the speech in the video.

## Contributing

Contributions to this project are welcome! Feel free to fork the repository, make your changes, and submit a pull request.


## Contact

If you have any questions or issues, please feel free to open an issue on the GitHub repository.
```
