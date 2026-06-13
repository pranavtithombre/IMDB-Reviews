# IMDB Sentiment Analysis

A simple Flask-based web application that predicts the sentiment of IMDb movie reviews using a pre-trained Machine Learning model.

## Features

* Web interface for entering movie reviews
* Predicts sentiment (Positive/Negative)
* Uses a pre-trained model stored in `model.pkl`
* Built with Flask
* Easy to deploy and extend

---

## Project Structure

```text
IMDb-Sentiment-Analysis/
│
├── app.py              # Flask application
├── model.pkl           # Trained sentiment analysis model
├── requirements.txt    # Python dependencies
└── README.md           # Project documentation
```

---

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/imdb-sentiment-analysis.git
cd imdb-sentiment-analysis
```

### 2. Create a Virtual Environment (Optional)

```bash
python -m venv venv
```

Activate the environment:

**Windows**

```bash
venv\Scripts\activate
```

**Linux/macOS**

```bash
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install flask
```

Or install from requirements file:

```bash
pip install -r requirements.txt
```

---

## Running the Application

Start the Flask server:

```bash
python app.py
```

The application will be available at:

```text
http://127.0.0.1:5000/
```

---

## How It Works

1. User enters a movie review.
2. Flask receives the review through a POST request.
3. The review is passed to the trained model.
4. The model predicts the sentiment.
5. The result is displayed on the webpage.

---

## Model Notes

The application currently loads a trained model using:

```python
with open("model.pkl", "rb") as f:
    model = pickle.load(f)
```

### Important

If your model was trained using:

* TF-IDF Vectorizer
* CountVectorizer
* Any custom preprocessing pipeline

You must also load the corresponding vectorizer and transform the review before prediction.

Example:

```python
with open("vectorizer.pkl", "rb") as f:
    vectorizer = pickle.load(f)

review_vector = vectorizer.transform([review])
prediction = model.predict(review_vector)[0]
```

---

## Example Review

**Input**

```text
This movie was amazing! The acting was brilliant and the story was captivating.
```

**Output**

```text
Positive
```

---

## Technologies Used

* Python
* Flask
* Scikit-learn
* Pickle
* HTML

---

## Future Improvements

* Add Bootstrap UI
* Display prediction confidence score
* Docker support
* Deploy on Render/Heroku
* Support batch predictions
* Add model performance metrics

---

## License

This project is licensed under the MIT License.

---

## Author

Your Name

GitHub: https://github.com/your-username
