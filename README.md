🎵 Music Recommendation Engine

An end-to-end music recommendation system powered by machine learning (k-Nearest Neighbors) and served via a FastAPI backend.

This project takes a dataset of songs and their audio features (e.g., tempo, valence, danceability) and provides song recommendations based on similarity — with no user history or preferences required.

🧠 Features
	•	Audio-Based Similarity: Recommendations are based on features like energy, tempo, valence, etc.
	•	k-NN Model: Uses cosine distance in a scaled feature space to find similar tracks.
	•	FastAPI Backend:
	•	POST /recommendations: Get recommendations for one or more track IDs
	•	GET /songs: Browse the full list of songs with pagination
	•	No Database Required: Songs and model are loaded from CSV and NumPy files
	•	Similarity Scoring: Results are ranked by how close they are in sound profile

🚀 Endpoints

1. POST `/recommendations` - Returns recommended songs based on track ID(s).
```
{
  "track_ids": ["0xq4ZTcmwBfkPGo4RRKmMe", "61uyGDPJ06MkxJtHgPmuyO"],
  "top_n": 5
}
```
2. GET `/songs` - Fetches songs with pagination.
```
GET /songs?page=1&limit=10
```

🛠 Tech Stack
	•	Python
	•	scikit-learn (for k-NN model)
	•	FastAPI (for backend)
	•	Pydantic (for request validation)
	•	NumPy + Pandas (for data processing)

✅ How to Run
1.	Install dependencies - `pip install -r requirements.txt`
2.	Run the API - `uvicorn app:app --reload`
3.	Access Swagger docs at - `http://localhost:8000/docs`
