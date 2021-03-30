# RecSysPapers

A summary of the most recent papers from the [@mtg-upf](https://github.com/MTG) on music recommender systems.

## Papers:

* Andres Ferraro et al.:
  * [Automatic playlist continuation using a hybrid recommender system combining features from text and audio
](#automatic-playlist-continuation-using-a-hybrid-recommender-system-combining-features-from-text-and-audio)
  * [Using offline metrics and user behavior analysis to combine multiple systems for music recommendation](#using-offline-metrics-and-user-behavior-analysis-to-combine-multiple-systems-for-music-recommendation)
  * [Skip prediction using boosting trees based on acoustic features of tracks in sessions](#skip-prediction-using-boosting-trees-based-on-acoustic-features-of-tracks-in-sessions)
  * [Artist and style exposure bias in collaborative filtering based music recommendations](#artist-and-style-exposure-bias-in-collaborative-filtering-based-music-recommendations)
  * [Exploring Longitudinal Effects of Session-based Recommendations](#exploring-longitudinal-effects-of-session-based-recommendations)
  * [Melon Playlist Dataset, a public dataset for audio-based playlist generation and music tagging](#melon-playlist-dataset-a-public-dataset-for-audio-based-playlist-generation-and-music-tagging)
  * [Enriched Music Representations with Multiple Cross modal Contrastive Learning](#enriched-music-representations-with-multiple-cross-modal-contrastive-learning)
* Schedl et al.:
  * [Music Recommendation Systems Techniques Use cases and Challenges](#music-recommendation-systems-techniques-use-cases-and-challenges)
## Summaries

### Andres Ferraro et al.:
#### Automatic playlist continuation using a hybrid recommender system combining features from text and audio
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed eiusmod tempor incidunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquid ex ea commodi consequat. Quis aute iure reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint obcaecat cupiditat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. 
> Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed eiusmod tempor incidunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquid ex ea commodi consequat. Quis aute iure reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint obcaecat cupiditat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. 


### Using offline metrics and user behavior analysis to combine multiple systems for music recommendation
fdsfd

### Skip prediction using boosting trees based on acoustic features of tracks in sessions
fsddfsf

### Artist and style exposure bias in collaborative filtering based music recommendations
fdsfdsfd

### Exploring Longitudinal Effects of Session-based Recommendations
fdsfdsf

### Melon Playlist Dataset, a public dataset for audio-based playlist generation and music tagging
fdsfd

### Enriched Music Representations with Multiple Cross modal Contrastive Learning
fdsfd

## Schedl et al.;
### Music Recommendation Systems Techniques Use cases and Challenges
Intro: granulation (what do we recommend? artists? albums? songs?). Repetition might be desirable. Automatic playlist continuation or Next-track recommendation. Not skipping does  not imply preference (might not be listening). Collaborative Filtering (Netflix Prize) vs. Content-Based Filtering (MIR).

USE CASES:
-
- SIMPLE RECOMMENDATION => people who played that also played this. Feedback: platforms gather 1-5 ratins or binary likes or shop history (e.g. iTunes), but it is easier to count the plays (no required interaction/distraction) and track skips = implicit feedback. This presents some problems (e.g. when ironically listening to stuff) that are usually minimized by filtering tracks not almost fully listened. Offline evaluation: retain part of the user behavior and measure RMSE or MAP@500 of ranked lists or normalized discounted cumulative gain (NDCG). Datasets KDD Cup 2011 or MSD.

- LEAN-IN EXPLORATION => as in Spotify. Starts with a text query (answers built on knowledge graphs, playlist titles from other users, tags and info from websites like "90s band with female singer"). Eval metric (from 2018 RecSys Challenge): R-precision, NDCG and Spotify metric. Here users are willing to devote time and attention to the system to enhance their personal experience.

- LEAN-BACK LISTENING => minimal user interaction (e.g. driving), out of sight. No choice further than skip. Song seeds playlist. Playlists are evaluated against real playlists. Listenning log data is cheap, but riscky (e.g. WSDM Cup 2019). Metric is MeanAverageAccuracy  (typo and means MAP@?). Tends to be more conservative than lean-in. A problem: skip prediction methods are trained and evaluated with historical data, with bias by that recommender. Playlist data might also be biased by curators.

- Other: recommending events of local long-tail artists, playlist discovery and recommendation, recommend background music for video (multi-modal)

TYPES OF MUSIC RECOMMENDER SYSTEMS

- COLLABORATIVE FILTERING: solely on user-item interactions data. Has community bias, popularity bias ([long-tail property of consumption behavior](https://www.youtube.com/watch?v=0Yku0GTrcuw)).
- CONTENT-BASED FILTERING: extract with NNs or with crafted features. [van den Oord's paper](https://proceedings.neurips.cc/paper/2013/file/b3ba8f1bee1238a2f37603d90b58898d-Paper.pdf) => CNN to predict user-item latent factors from matrix factorization of collaborative filtering data, then we can compute distance from audio-only to profile. Also profile latent sapces by averaging all tracks in a profile. 
- HYBRID APPROACH: or uses several data sources, or several recommendation techniques. Oramas approach, which uses biographies.
- CONTEXT-AWARE: contextual pre-filtering => only the  portion  of the data that fits the user context is chosen. contextual post-filtering => first we recommend, then we adjust conditioned on context. We can also extend latent factor models by contextual dimensions (concat or gating).
- SEQUENTIAL: use CNN + RNN.
- PSYCHOLOGY-INSPIRED: consider frequency of exposure and recentness of exposure, and integrates in ACT-R (adaptive control of thought-rational) psychologic model. Use personality for expanding the latent factor.

CHALLENGES

- Objectives: match user's preferences, be similar to the user's preferred tracks but at the same time diverse (not boring), familiar and novel ("even for users that prefer novel music, familiarity is a positive predictor), trendy/popular (for mitigating cold start users), be coherent.
- How to consider user intrinsic data in cold start? Use data from elsewhere.
- How to make them fair?
- How to explain them? (BAndits for Recsplanations as Treatments by Spotify)
- How to evaluate?
