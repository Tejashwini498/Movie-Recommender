# 🎬 CineMatch — Movie Recommendation System

A machine learning project that recommends movies based on what you like. Built with Python and Flask, it combines multiple recommendation techniques to suggest films you'll actually enjoy — not just popular ones everyone's seen.

![Python](https://img.shields.io/badge/Python-3.10+-blue?style=flat-square)
![Flask](https://img.shields.io/badge/Flask-3.0-green?style=flat-square)
![scikit-learn](https://img.shields.io/badge/scikit--learn-1.4-orange?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-purple?style=flat-square)

---

## Why I built this

With thousands of movies available across platforms, finding something good to watch is genuinely hard. Browsing endlessly doesn't work. This project tries to solve that by learning from movie attributes and user behavior to surface relevant recommendations automatically.

---

## What it does

- Recommends movies similar to ones you already like
- Learns from ratings across users to find patterns
- Lets you search by title, genre, director, or vibe
- Updates recommendations as you rate more movies
- Exposes everything through a clean REST API

---

## How the ML works

There are three recommendation strategies running under the hood:

**Content-Based Filtering** looks at each movie's genres, director, cast, and plot summary. It converts all of that into vectors using TF-IDF and finds movies that are mathematically similar to ones you've liked.

**Collaborative Filtering** looks at what users similar to you have rated highly. If someone with your taste loved a film you haven't seen yet, it surfaces that.

**Hybrid** combines both scores (60% content, 40% collaborative) so you get recommendations that are both similar in style and validated by real user behavior.

---

## Tech Stack

- **Backend** — Python, Flask, Flask-CORS
- **ML** — scikit-learn (TF-IDF, cosine similarity), pandas, numpy
- **Frontend** — HTML, CSS, Vanilla JavaScript
- **Storage** — SQLite / CSV

---

## Project Structure
movie-recommender/
├── app.py               # Flask API and routes
├── create_files.py      # Builds the dataset and trains the model
├── data/                # Movie and ratings data
├── model/               # Saved ML models
├── static/              # Frontend assets
├── templates/           # HTML pages
├── requirements.txt
└── README.md

---

## Getting Started

```bash
# Clone the repo
git clone https://github.com/<your-username>/movie-recommender.git
cd movie-recommender

# Set up virtual environment
python -m venv venv
venv\Scripts\activate        # Windows
source venv/bin/activate     # Mac/Linux

# Install dependencies
pip install -r requirements.txt

# Generate data and train the model
python create_files.py

# Start the app
python app.py
```

Then open **http://127.0.0.1:5000** in your browser.

---

## API Endpoints

| Method | Endpoint | What it does |
|--------|----------|--------------|
| GET | `/` | Home page |
| GET | `/api/movies` | All movies |
| GET | `/api/movies/toprated` | Top rated films |
| GET | `/api/movies/popular` | Most popular |
| GET | `/api/search?q=` | Search by query |
| GET | `/api/recommend/<id>` | Similar movies |
| GET | `/api/recommend/user/<id>` | Picks for a user |
| POST | `/api/rate` | Submit a rating |
| GET | `/api/genres` | All genres |
| GET | `/api/stats` | Dataset overview |

---

## License

MIT — feel free to use, modify, or build on this.
