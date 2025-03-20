# Song_Recommendation_System
A smart system that recommends songs based on user preferences, listening history, and song features using machine learning techniques like collaborative and content-based filtering for a personalized music experience.
Here’s a clean **README** template for your **Song Recommendation System** project, built in **Google Colab**. You can customize it further if needed.

---

## 🎵 Song Recommendation System

This project is a **music recommendation system** that suggests songs based on user input using **hybrid filtering** (content + collaborative). Built and run in **Google Colab**.

---

### 🚀 Features
- Normalizes music features using **Min-Max Scaling**
- Uses **cosine similarity** to find similar songs
- Provides **hybrid recommendations** based on both song features and popularity
- Integrates with **Spotify playlists** (manual data or via API)

---

### 📂 Files
- `music_data.csv` – Dataset containing song features *(upload this to Colab)*
- `recommendation_system.ipynb` – Main Colab notebook

---

### 🛠️ Requirements
- Python 3.x
- Libraries:
  - pandas
  - numpy
  - sklearn
  - scipy
  - (optional) spotipy – for Spotify API integration

Install (if needed):
```python
!pip install pandas numpy scikit-learn scipy spotipy
```

---

### 📊 Dataset Columns (Example)
- `track_name`
- `artist`
- `danceability`
- `energy`
- `key`
- `loudness`
- `mode`
- `speechiness`
- `acousticness`
- `instrumentalness`
- `liveness`
- `valence`
- `tempo`

---

### 📌 Usage
1. Upload your dataset:
   ```python
   from google.colab import files
   uploaded = files.upload()
   ```

2. Load data:
   ```python
   import pandas as pd
   music_df = pd.read_csv('music_data.csv')
   ```

3. Normalize features:
   ```python
   from sklearn.preprocessing import MinMaxScaler
   scaler = MinMaxScaler()
   features = ['danceability', 'energy', 'key', 'loudness', 'mode', 
               'speechiness', 'acousticness', 'instrumentalness', 
               'liveness', 'valence', 'tempo']
   music_features = music_df[features].values
   music_features_scaled = scaler.fit_transform(music_features)
   ```

4. Get recommendations:
   ```python
   input_song_name = "I'm Good (Blue)"
   recommendations = hybrid_recommendations(input_song_name, num_recommendations=5)
   print(recommendations)
   ```

---

### 🎯 Output
```
Hybrid recommended songs for 'I'm Good (Blue)':
['Song A', 'Song B', 'Song C', 'Song D', 'Song E']
```

---

### 💡 Note
- Make sure the song exists in your dataset.
- Use the **Spotify Web API** for dynamic playlist/track data.

---
