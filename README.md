# Sentiment Analysis with Transformers

This project demonstrates how to use the Hugging Face Transformers library to perform sentiment analysis on text using a pre-trained model.

## Installation

```bash
pip install transformers torch
```

## Usage

The script uses the `pipeline` feature from the Transformers library to perform sentiment analysis. The default model will classify text as either POSITIVE or NEGATIVE with a confidence score.

```python
from transformers import pipeline
sentiment_pipeline = pipeline("sentiment-analysis")

# Example usage
result = sentiment_pipeline("Your text here")
print(result)
```

## Example Results

The script analyzes various types of text, from news headlines to longer content pieces:

1. News about protests:
```python
print(sentiment_pipeline(' 120 arrested at NYU while Columbia donor pulls funding as pro-Palestine protests sweep college campuses'))
# Output: [{'label': 'NEGATIVE', 'score': 0.9991}]
```

2. Tragic news:
```python
print(sentiment_pipeline('Girl, 7, among five dead on Channel migrant boat'))
# Output: [{'label': 'NEGATIVE', 'score': 0.9997}]
```

3. TV show review:
```python
print(sentiment_pipeline('People around the world have been captivated by Baby Reindeer...'))
# Output: [{'label': 'NEGATIVE', 'score': 0.9634}]
```

4. Financial analysis:
```python
print(sentiment_pipeline('Gold completed a 50% retracement today...'))
# Output: [{'label': 'POSITIVE', 'score': 0.9926}]
```

5. Product safety news:
```python
print(sentiment_pipeline('Everyone knows them, kids everywhere love them. Lunchables...'))
# Output: [{'label': 'NEGATIVE', 'score': 0.9947}]
```

## Notes

- The sentiment analysis model provides binary classification (POSITIVE/NEGATIVE)
- The score indicates the confidence level of the classification
- The model can process both short headlines and longer text passages
- Results show that the model effectively captures emotional tone in various contexts

## Limitations

- The model provides binary sentiment only (positive/negative)
- Context and nuance might be lost in complex topics
- Sentiment analysis may not always align with human interpretation

## Dependencies
- transformers
- torch (installed automatically with transformers)

## License
This project uses the Hugging Face Transformers library, which is licensed under the Apache License 2.0.
