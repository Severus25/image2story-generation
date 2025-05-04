# image2story-generation
## Story Generator from Image

This project allows you to generate a short story based on an uploaded image. The process involves converting the image into text using an image-to-text model, then generating a short story from the text, and finally converting the story into speech.

### Key Features:
- **Image-to-Text Conversion**: Using a pre-trained model to convert the content of an image into descriptive text.
- **Story Generation**: The system generates a short, creative story based on the extracted text using language models.
- **Text-to-Speech**: The generated story is converted into speech, allowing the user to listen to the story.

### Technologies Used:
- **Streamlit**: For building the interactive web app interface.
- **Hugging Face Transformers**: For the image-to-text, story generation, and text-to-speech models.
- **Langchain**: For generating creative and context-aware stories.
- **Gemini API**: For story generation using the Gemini-1.5-turbo model.

---

## Prerequisites

Before running the project, ensure you have the following installed:

- Python 3.7+
- Pip package manager
- A Hugging Face API token (for accessing models and converting text to speech)

---

## Installation Instructions

### 1. Clone the Repository

Clone the repository to your local machine using Git:

```bash
git clone https://github.com/Severus25/image2story-generation.git
cd image2story-generation
```

### 2. Install Dependencies
Use pip to install the necessary Python packages. It's recommended to create a virtual environment to manage dependencies.

Install dependencies:
``` bash
pip install -r requirements.txt
```

If you don't have a requirements.txt file, you can manually install the following dependencies:

``` bash
pip install streamlit transformers langchain requests python-dotenv
```

### 3. Set Up Environment Variables
You need to provide your Hugging Face API token to access certain models. Create a .env file in the root directory of the project and add the following:

```bash
HUGGINGFACE_API_TOKEN=your_huggingface_api_token_here
```
Replace your_huggingface_api_token_here with your actual Hugging Face API token. You can obtain this token by signing up for an account at Hugging Face.

How to Use
1. Launch the Web Application
To run the app, use the following command:

``` bash
streamlit run app.py
```

This will launch the application in your default web browser. If everything is set up correctly, you will see the following interface:

A file upload button to choose an image (JPG, JPEG, PNG).

A button to generate a story based on the uploaded image.

Display of the generated story and an audio player to listen to the story.

---

2. Upload an Image
Click on the "Choose an image..." button to upload an image. The application will automatically process the image, extract a description from it, and generate a story.

---

3. View the Results
Once the image is uploaded and processed, the following will be displayed:

Scenario: The text description of the image.

Story: A short, creative story generated from the image description.

Audio: An audio file of the story that you can listen to.

---

### Project Structure
``` bash
├── app.py                # Main application script
├── requirements.txt      # List of project dependencies
├── .env                  # Environment variables (Hugging Face API token)
├── audio.flac            # Temporary audio file for the story
└── README.md             # This file
```
---

### How It Works
Image-to-Text (img2text):

The image is uploaded through the Streamlit interface.

The image is passed to the Salesforce/blip-image-captioning-base model from Hugging Face to generate a textual description of the image.

Story Generation (generate_story):

The textual description (or scenario) of the image is passed to the Gemini model (gemini-1.5-turbo) via the langchain library to generate a short story.

Text-to-Speech (text2speech):

The generated story is sent to the espnet/kan-bayashi_ljspeech_vits model on Hugging Face to convert the text into speech.

The speech is saved as an audio file (audio.flac), which is made available to the user in the Streamlit interface.

---

### Future Improvements
Error Handling: Add better error handling for invalid images or issues with Hugging Face models.

Multi-Language Support: Extend the text-to-speech capability to support multiple languages.

Story Length Control: Allow users to set a custom length for the generated story.

Model Enhancements: Explore using more advanced or fine-tuned models for better image captioning and story generation.

---

### Contributing
Contributions are welcome! If you'd like to contribute to this project, feel free to fork the repository, make your changes, and create a pull request.

---

### License
This project is licensed under the MIT License - see the LICENSE file for details.

---

### Acknowledgements
Hugging Face for providing pre-trained models and APIs for text generation and image captioning.

Streamlit for making it easy to build web applications with Python.

Langchain for simplifying the usage of large language models.

---
