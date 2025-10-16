# 🎬 Movie Recommender System

A sophisticated movie recommendation system built with Streamlit that provides personalized movie suggestions based on multiple factors including genres, cast, keywords, production companies, and more.

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Streamlit](https://img.shields.io/badge/Streamlit-1.0+-red.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)

## 📋 Table of Contents

- [Features](#features)
- [Demo](#demo)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [How It Works](#how-it-works)
- [Technologies Used](#technologies-used)
- [API Integration](#api-integration)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## ✨ Features

### 🎯 Multi-Factor Recommendations
- *Genre-Based*: Discover movies from similar genres
- *Cast-Based*: Find movies featuring your favorite actors
- *Keyword-Based*: Explore movies with similar themes and plot elements
- *Production Company*: Get recommendations from the same studios
- *Tag-Based*: Comprehensive similarity matching

### 🎭 Movie Details
- High-quality movie posters
- Comprehensive movie information (rating, runtime, budget, revenue)
- Detailed overview and synopsis
- Release date and availability
- Director information

### 👥 Cast Information
- Display of top 5 cast members
- Actor images and biographies
- Interactive toggles for expanded information

### 📚 Browse All Movies
- Paginated movie gallery
- Smooth navigation with prev/next buttons
- Slider for quick page jumping
- Display of 10 movies per page

## 🚀 Demo

[Add screenshots or GIF demonstrations of your application here]

## 📦 Installation

### Prerequisites

- Python 3.8 or higher
- pip package manager
- TMDB API key (for fetching movie data)

### Steps

1. *Clone the repository*
bash
git clone https://github.com/yourusername/movie-recommender-system.git
cd movie-recommender-system


2. *Create a virtual environment*
bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate


3. *Install required packages*
bash
pip install -r requirements.txt


4. *Set up API credentials*
- Create a file config.py or .env file
- Add your TMDB API key:
python
TMDB_API_KEY = "your_api_key_here"


5. *Prepare the data files*
- Ensure all pickle files are in the Files/ directory:
  - similarity_tags_tags.pkl
  - similarity_tags_genres.pkl
  - similarity_tags_tprduction_comp.pkl
  - similarity_tags_keywords.pkl
  - similarity_tags_tcast.pkl

## 🎮 Usage

1. *Run the application*
bash
streamlit run app.py


2. *Access the web interface*
- Open your browser and navigate to http://localhost:8501

3. *Choose your option*
   - *Recommend me a similar movie*: Select a movie and get personalized recommendations
   - *Describe me a movie*: View detailed information about a specific movie
   - *Check all Movies*: Browse through the entire movie database

## 📁 Project Structure


movie-recommender-system/
│
├── app.py                          # Main application file
├── requirements.txt                # Python dependencies
├── README.md                       # Project documentation
│
├── processing/
│   ├── __init__.py
│   ├── preprocess.py              # Data preprocessing and recommendation logic
│   └── display.py                 # Display utilities (Main class)
│
├── Files/
│   ├── similarity_tags_tags.pkl
│   ├── similarity_tags_genres.pkl
│   ├── similarity_tags_tprduction_comp.pkl
│   ├── similarity_tags_keywords.pkl
│   └── similarity_tags_tcast.pkl
│
└── data/
    └── [Your movie dataset files]


## 🔧 How It Works

### Recommendation Algorithm

The system uses *cosine similarity* on multiple feature vectors to generate recommendations:

1. *Feature Extraction*: Movies are analyzed across multiple dimensions (genres, cast, keywords, tags, production companies)

2. *Similarity Calculation*: For each feature type, a similarity matrix is computed using cosine similarity

3. *Multi-Factor Recommendation*: When a user selects a movie, the system:
   - Retrieves top similar movies from each similarity matrix
   - Filters out duplicates across categories
   - Returns the top 5 unique recommendations per category

4. *Data Fetching*: Movie posters and details are fetched in real-time using the TMDB API

### Key Components

- *Session State Management*: Streamlit session state tracks user selections and pagination
- *Dynamic UI*: Option menu provides intuitive navigation between features
- *Real-time API Integration*: Fetches fresh movie data and images on demand

## 🛠 Technologies Used

- *Frontend*: Streamlit, streamlit-option-menu, streamlit-extras
- *Backend*: Python
- *Data Processing*: Pandas, NumPy, Pickle
- *Machine Learning*: Scikit-learn (for similarity calculations)
- *API*: TMDB (The Movie Database) API
- *Deployment*: Can be deployed on Streamlit Cloud, Heroku, or AWS

## 🔌 API Integration

This project uses The Movie Database (TMDB) API:

1. Sign up at [TMDB](https://www.themoviedb.org/)
2. Generate your API key from account settings
3. Use the API to fetch:
   - Movie posters
   - Movie details (budget, revenue, runtime, ratings)
   - Cast information and biographies
   - Director information

## 📊 Dependencies

txt
streamlit
streamlit-option-menu
streamlit-extras
pandas
numpy
pickle
requests
scikit-learn


## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a new branch (git checkout -b feature/AmazingFeature)
3. Commit your changes (git commit -m 'Add some AmazingFeature')
4. Push to the branch (git push origin feature/AmazingFeature)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- TMDB for providing the comprehensive movie database API
- Streamlit team for the amazing framework
- The open-source community for various libraries used

## 📧 Contact

Your Name - [@yourtwitter](https://twitter.com/yourtwitter) - your.email@example.com

Project Link: [https://github.com/yourusername/movie-recommender-system](https://github.com/yourusername/movie-recommender-system)

---

⭐ If you found this project helpful, please give it a star!

## 🐛 Known Issues

- Large datasets may cause initial load time
- API rate limiting may affect image loading speed

## 🔮 Future Enhancements

- [ ] Add user authentication and personalized watchlists
- [ ] Implement collaborative filtering based on user ratings
- [ ] Add movie trailers and streaming availability
- [ ] Include social features (reviews, ratings)
- [ ] Mobile app version
- [ ] Advanced search and filtering options
- [ ] Machine learning model improvements
