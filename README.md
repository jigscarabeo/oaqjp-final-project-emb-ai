# oaqjp-final-project-emb-ai

## Emotion Detection Web App

An AI-based Flask web application that analyzes customer feedback text and identifies the emotion it expresses. It returns scores for anger, disgust, fear, joy, and sadness, plus the dominant emotion.

Built for an e-commerce company to support analytics on customer feedback for its signature products.

## Features

- Emotion detection using the Watson NLP EmotionPredict service
- Packaged as an importable Python module (`EmotionDetection`)
- Flask web interface for entering feedback and viewing results
- Error handling for blank or invalid input
- Unit tests and static code analysis (pylint 10/10)

## Project Structure

```
oaqjp-final-project-emb-ai/
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

- Python 3
- `requests`
- `flask`

```
python3 -m pip install requests flask
```

## Usage

Run the web app:

```
python3 server.py
```

Open the app on port 5000, enter a statement, and click **Run Emotion Detection**. Blank input returns `Invalid text! Please try again!`

Use the function directly:

```python
from EmotionDetection.emotion_detection import emotion_detector

print(emotion_detector("I love my life"))
```

Example output:

```
{'anger': 0.006274985, 'disgust': 0.0025598293, 'fear': 0.009251528, 'joy': 0.9680386, 'sadness': 0.049744144, 'dominant_emotion': 'joy'}
```

## Running the Tests

```
python3 test_emotion_detection.py
```

## Static Code Analysis

```
python3 -m pip install pylint
pylint server.py
```

## Notes

The Watson endpoint used here is typically reachable only from within the IBM Skills Network lab environment.

## Author

Eduardo P. Carabeo Jr.
