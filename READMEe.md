Song Recommender
Description:
The recommender.ipynb script is designed to provide song recommendations based on user input and historical data. Utilizing advanced algorithms, it ensures accurate and relevant song suggestions.

Requirements:
Python 3.x
pandas
numpy
spotipy (for Spotify API integration)
How to Run:
Ensure you have all the required libraries installed.
Navigate to the directory containing the recommender.ipynb script.
Run the command: python recommender.ipynb
Features:
User-based recommendation
Item-based recommendation
Hybrid recommendation approach
Spotify API integration for fetching song URLs
Data Preparation:
The script reads two datasets, hot and not_hot, which contain information about songs, including their features.
An extra id column that's not needed is dropped.
A 'hot' column is added to both datasets to label whether each song is hot ('Yes' for hot songs and 'No' for not hot songs).
The 'hot' and 'not hot' datasets are concatenated into a single dataframe named all_songs, combining both sets of songs for clustering.
Data is scaled to have a mean of 0 and a standard deviation of 1 using StandardScaler. The scaling parameters are saved for later use.
K-Means Clustering:
K-Means clustering is performed on the scaled data for different values of k.
The inertia and silhouette score for each k are calculated to determine the optimal number of clusters. The optimal value appears to be k=3 based on the silhouette score.
Songs are assigned to their respective clusters, and a 'clusters' column is added to the all_songs dataframe.
Spotify API Integration:
The script integrates with the Spotify API using the spotipy library.
Functions are defined to fetch the Spotify URL for a given song and artist and to recommend a song based on user input.
User Interaction & Recommendation:
The user is prompted to input their favorite song and artist.
Based on the user's input and cluster information, the script retrieves the Spotify URL and other details for a recommended song.
The recommendation logic checks if the user's favorite song is in the 'hot' dataset. If it is, a song from 'hot' songs in the same cluster is recommended. Otherwise, a song from 'not hot' songs in the same cluster is suggested.
The recommended song title and its Spotify URL are displayed.
Exporting Data:
The dataframe with cluster information is exported to a CSV file named 'all_songs_clustered.csv'.
Author:
Faryal, Chibudem, Rodrigo

