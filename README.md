# RecSysPapers

A summary of papers from the [@mtg-upf](https://github.com/MTG) and others, mainly on music recommender systems.

## List of readings
* Schedl et al.:
  * [Music Recommendation Systems Techniques Use cases and Challenges](#music-recommendation-systems-techniques-use-cases-and-challenges)
* Andres Ferraro et al.:
  * [Automatic playlist continuation using a hybrid recommender system combining features from text and audio
](#automatic-playlist-continuation-using-a-hybrid-recommender-system-combining-features-from-text-and-audio)
  * [Using offline metrics and user behavior analysis to combine multiple systems for music recommendation](#using-offline-metrics-and-user-behavior-analysis-to-combine-multiple-systems-for-music-recommendation)
  * [Skip prediction using boosting trees based on acoustic features of tracks in sessions](#skip-prediction-using-boosting-trees-based-on-acoustic-features-of-tracks-in-sessions)
  * [Artist and style exposure bias in collaborative filtering based music recommendations](#artist-and-style-exposure-bias-in-collaborative-filtering-based-music-recommendations)
  * [Exploring Longitudinal Effects of Session-based Recommendations](#exploring-longitudinal-effects-of-session-based-recommendations)
  * [Melon Playlist Dataset, a public dataset for audio-based playlist generation and music tagging](#melon-playlist-dataset-a-public-dataset-for-audio-based-playlist-generation-and-music-tagging)
  * [Enriched Music Representations with Multiple Cross modal Contrastive Learning](#enriched-music-representations-with-multiple-cross-modal-contrastive-learning)

* Blogs:
  * [ALS Implicit Collaborative Filtering](#als-implicit-collaborative-filtering)
  * [Distance Metrics for Fun and Profit](#distance-metrics-for-fun-and-profit)
  * [Genre Essentials](#genre-essentials)
  * [Evaluating recommender systems](#evaluating-recommender-systems)
  
## Summaries
## Schedl et al.;
### Music Recommendation Systems Techniques Use cases and Challenges
[Link here](https://www.researchgate.net/journal/International-Journal-of-Multimedia-Information-Retrieval-2192-662X/publication/320296777_Current_Challenges_and_Visions_in_Music_Recommender_Systems_Research/links/5fc46def299bf104cf942321/Current-Challenges-and-Visions-in-Music-Recommender-Systems-Research.pdf), which links to [this](https://www.youtube.com/watch?v=9gBC9R-msAk) video about LightFM library and [this](https://www.youtube.com/watch?v=ZspR5PZemcs) to the method description.
Intro: granulation (what do we recommend? artists? albums? songs?). Repetition might be desirable. Automatic playlist continuation or Next-track recommendation. Not skipping does  not imply preference (might not be listening). Collaborative Filtering (Netflix Prize) vs. Content-Based Filtering (MIR).

USE CASES:
![icon](https://www.researchgate.net/profile/Lionel-Ngoupeyou-Tondji/publication/323726564/figure/fig5/AS:631605009846299@1527597777415/Content-based-filtering-vs-Collaborative-filtering-Source.png)
- SIMPLE RECOMMENDATION => people who played that also played this. Feedback: platforms gather 1-5 ratins or binary likes or shop history (e.g. iTunes), but it is easier to count the plays (no required interaction/distraction) and track skips = implicit feedback. This presents some problems (e.g. when ironically listening to stuff) that are usually minimized by filtering tracks not almost fully listened. Offline evaluation: retain part of the user behavior and measure RMSE or MAP@500 of ranked lists or normalized discounted cumulative gain (NDCG). Datasets KDD Cup 2011 or MSD.
- LEAN-IN EXPLORATION => as in Spotify. Starts with a text query (answers built on knowledge graphs, playlist titles from other users, tags and info from websites like "90s band with female singer"). Eval metric (from 2018 RecSys Challenge): R-precision, NDCG and Spotify metric. Here users are willing to devote time and attention to the system to enhance their personal experience.
- LEAN-BACK LISTENING => minimal user interaction (e.g. driving), out of sight. No choice further than skip. Song seeds playlist. Playlists are evaluated against real playlists. Listenning log data is cheap, but riscky (e.g. WSDM Cup 2019). Metric is MeanAverageAccuracy  (typo and means MAP@?). Tends to be more conservative than lean-in. A problem: skip prediction methods are trained and evaluated with historical data, with bias by that recommender. Playlist data might also be biased by curators.
- Other: recommending events of local long-tail artists, playlist discovery and recommendation, recommend background music for video (multi-modal)

TYPES OF MUSIC RECOMMENDER SYSTEMS

- COLLABORATIVE FILTERING: solely on user-item interactions data. Has community bias, popularity bias ([long-tail property of consumption behavior](https://www.youtube.com/watch?v=0Yku0GTrcuw)).
- CONTENT-BASED FILTERING: on user-item ratings, find similar items with features or DNNS->[van den Oord's paper](https://proceedings.neurips.cc/paper/2013/file/b3ba8f1bee1238a2f37603d90b58898d-Paper.pdf) => CNN to predict user-item latent factors from matrix factorization of collaborative filtering data, then we can compute distance from audio-only to profile. Also profile latent sapces by averaging all tracks in a profile. 
- HYBRID APPROACH: or uses several data sources, or several recommendation techniques. Oramas approach, which uses biographies.
- CONTEXT-AWARE: contextual pre-filtering => only the  portion  of the data that fits the user context is chosen. contextual post-filtering => first we recommend, then we adjust conditioned on context. We can also extend latent factor models by contextual dimensions (concat or gating).
- SEQUENTIAL: use CNN + RNN.
- PSYCHOLOGY-INSPIRED: consider frequency of exposure and recentness of exposure, and integrates in ACT-R (adaptive control of thought-rational) psychologic model. Use personality for expanding the latent factor.

CHALLENGES

- Objectives: match user's preferences, be similar to the user's preferred tracks but at the same time diverse (not boring), familiar and novel ("even for users that prefer novel music, familiarity is a positive predictor), trendy/popular (for mitigating cold start users), be coherent.
- How to consider user intrinsic data in cold start? Use data from elsewhere.
- How to make them fair?
- How to explain them? (BAndits for Recsplanations as Treatments by Spotify)
- How to evaluate? High accuracy != user satisfaction. Existing datasets don't cover familiarity with items. In industrial settings: online evaluation with A/B testing. Dmitry combines liking, familiarity, listening intention and "give-me-more" into trusts, hits and fails.
- How to deal with missing and negative feedback in evaluation? Using meta-data from the same user-artist, for example.
- How to design UX that match the use case and increase experience? Different personalities prefer different organization principles.

### Andres Ferraro et al.:
#### Automatic playlist continuation using a hybrid recommender system combining features from text and audio
Andres describes his RecSys18 systems. Treats playlists as tracks, and makes a tracks-playlists matrix. Collaborative filtering + metadata (with Essentia-genre + normalized playlist titles). Methods are Matrix Factorization model and Track proximity model, then combines them. Matrix Factorization from [this](https://arxiv.org/pdf/1507.08439.pdf) paper: matrix humans-movies (values are ratings) 

------------------------------------------------------------------------------------------------------------

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



## Blogs
### ALS Implicit Collaborative Filtering
[Link here.](https://medium.com/radon-dev/als-implicit-collaborative-filtering-5ed653ba39fe)
### Distance Metrics for Fun and Profit
[Link here.](https://www.benfrederickson.com/distance-metrics/)
### Genre Essentials
[Link here.](https://towardsdatascience.com/genre-essentials-building-an-album-recommender-system-c89c308d16f0)
### Evaluating recommender systems
[Link here.](http://fastml.com/evaluating-recommender-systems/)
