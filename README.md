# Automatic-Indian-Sign-Language-Translation
A Flask web app that accepts typed English or speech captured through a supported browser and displays Indian Sign Language (ISL) GIFs and fingerspelling images.
<img width="1672" height="941" alt="image" src="https://github.com/user-attachments/assets/14a80a71-4d4d-433b-a2ea-2bd34125ec66" />
Project overview
The project demonstrates how common English phrases can be paired with recorded ISL signs in a browser. It provides two ways to enter a phrase: type directly into the text box or speak into a microphone in a supported browser. Both inputs use the same translation logic.
Dashboard preview

The mockup illustrates the input and output panels using the example phrase good morning.
How it works
1. Enter English text or use the microphone. The browser's speech recognition feature converts speech to text.
2. The app normalizes the text and looks for an exact match in its phrase dictionary.
3. If the full phrase has no matching GIF, the app looks up individual words. It fingerspells unfamiliar words using images for A–Z.
Implementation and scope
- Python and Flask serve the web page and handle translation requests. The POST /translate endpoint accepts a JSON object with a text field and returns an ordered list of signs or letter images.
- HTML, CSS and JavaScript handle the interface. Voice input uses the browser's speech recognition feature and requires microphone permission. Typed input is available independently of microphone access.
- Local media files supply phrase GIFs and A–Z images. The app checks for a bundled GIF before returning a dictionary match.
This is a dictionary-based prototype. Its phrase coverage depends on the GIFs bundled with the app. For an unfamiliar phrase, word lookup and fingerspelling preserve the English input order. The prototype does not model ISL grammar.
Run locally on Windows
Install Python, then open PowerShell in the project folder containing app.py and run:
py -m pip install Flask
py app.py
Open http://localhost:5000. To try voice input, use a browser that supports speech recognition and allow microphone access. You can use the text box directly for the examples below.
Try typing	Expected output
good morning	The matching phrase GIF
nice to meet you	The matching phrase GIF
xyz	Three fingerspelling images for X, Y and Z


Project structure
Path	Purpose
app.py	Flask routes, phrase lookup and fingerspelling
templates/	Web page template
static/	CSS and browser JavaScript
ISL_Gifs/	GIFs for words and phrases
letters/	Fingerspelling images
main1.py, main2.py	Desktop versions using Sphinx and Google speech recognition, respectively
signlang.png	README illustration
isl-dashboard.png	Dashboard mockup for the README


Credits
Based on the original Automatic Indian Sign Language Translator by Shubh Yadav, as credited in the source archive.
