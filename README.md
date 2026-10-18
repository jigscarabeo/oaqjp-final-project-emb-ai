# FINAL PROJECT

# Emotion Detection Web App

An AI-based Flask web application that analyzes customer feedback text and identifies the emotion it expresses. It returns scores for **anger, disgust, fear, joy, and sadness**, plus the **dominant emotion**.

Built for an e-commerce company to support analytics on customer feedback for its signature products.

## Features

- Emotion detection using the Watson NLP EmotionPredict service
- Packaged as an importable Python module (`EmotionDetection`)
- Flask web interface for entering feedback and viewing results
- Error handling for blank or invalid input
- Unit tests and static code analysis (pylint, 10/10)

## Project Structure

```
<repo-name>/
├── EmotionDetection/
│   ├── __init__.py
│   └── emotion_detection.py
├── static/
│   └── mywebscript.js
├── templates/
│   └── index.html
├── server.py
├── test_emotion_detection.py
└── README.md
```

## Requirements

- Python 3.8+
- `requests`
- `flask`

Install dependencies:

```bash
python3 -m pip install requests flask
```

## Usage

### Run the web app

```bash
python3 server.py
```

Open `http://localhost:5000`, enter a statement, and click **Run Emotion Detection**.

### Use the function directly

```python
from EmotionDetection.emotion_detection import emotion_detector

emotion_detector("I love this product!")
```

Example output:

```python
{'anger': 0.0059, 'disgust': 0.0007, 'fear': 0.0042,
 'joy': 0.9686, 'sadness': 0.0225, 'dominant_emotion': 'joy'}
```

### Example web response

```
For the given statement, the system response is 'anger': 0.0057, 'disgust': 0.0011,
'fear': 0.0039, 'joy': 0.9849 and 'sadness': 0.0160. The dominant emotion is joy.
```

Blank input returns:

```
Invalid text! Please try again!
```

## Running Tests

```bash
python3 -m unittest -v test_emotion_detection.py
```

## Static Code Analysis

```bash
python3 -m pip install pylint
pylint server.py
```

## Notes

The Watson endpoint used here is typically reachable only from within the IBM Skills Network lab environment.

## Author

EDUARDO P CARABEO JR
