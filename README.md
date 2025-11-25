
### Content Based approach to Language Agnostic Music Recommender

**Author**
Bhalchandra Gajare

#### Executive summary
This project implements a Proof Of Concept for a music recommendation system that does not need track metadata (eg: artist, user ratings, etc) or user similarity for recommending similar songs. Instead, the focus of the project is to use raw audio characteristics (ex: tone, rhythm, harmony, etc) to identify similar songs. This also makes the recommendation system agnostic to Language as the language is not considered as a acoustic property for the models trained in this project. Such a system can bring equity to music recommendation, where not just the most liked or highest rated music tracks are recommended, rather the recommendations are stemmed from the audio characteristics of the music that the user likes to listen to.

#### Rationale
1. Most current song recommendation engines (ex: spotify, youtube) perform a collaborative filtering with metadata and tags (user and item factors), This creates a 'bubble" where users are restricted to certain type of music, which is especially relevant to language (ex: english music listeners are not recommended with spanish or hindi language music tracks irrespective of thier likes)
2. A language agnostic music recommendation system unlocks new potential for streaming platforms, radios, etc to become a hub for exploring new music.
3. As a content creator or music director, users might be very interested in finding patterns and similarities in music accross language boundaries
4. The language agnostic nature of the system opens pathways for cross cultural content discovery.

#### Research Question
Can a recommendation system that uses only audio characteristics be effective in generating recommendations, purely based on acoustics without any other track metadata at all.


#### Data Sources
Used the GTZAN dataset from Kaggle 
1. This has 1000 tracks, each of 30 seconds in length
2. The audio format is mono (1 channel) and 22,050 Hz
3. The files are stored as .wav files (which are PCM encoded audio)
4. There are 10 distinct genres and each genre has 100 tracks

#### Methodology
The initial "Data Analysis" does these primary tasks 
1. Convert the audio wav files to spectral co-efficients using signal processing concepts (this uses `librosa`)
2. Using a pipeline with standard Scaler and K-nearest neighbors to setup a baseline model
3. Also predict neighbors for a external song that the model has never seen 

#### Results
The baseline KNN model has demonstrated strong capability to gruop the audio by characteristics. Especially when a external song (that the model has never listened to) is fed as input, we can clearly see that the recommendations are very close and very similar sounding. The external song fed was in Hindi with a lively upbeat track, the KNN model recommended similar lively and upbeat songs from the pop and hiphop genre.

#### Next steps
Improve the models recommendation by training a Deep Neural Network.

#### Outline of project

- Link to notebook 1 -- [cbmr_eda.ipynb](https://github.com/bgajare/ContentBasedMusicRecommend/blob/main/cbmr_eda.ipynb)


##### Contact and Further Information
