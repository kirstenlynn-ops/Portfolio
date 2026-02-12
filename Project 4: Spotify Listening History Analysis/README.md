# 🎧 Spotify Listening History Analysis (2022–2025)
- Prepared by: Kirsten Livingston

|Project Deliverables & Repository Access                                                                |
|--------------------------------------------------------------------------------------------------------|
|GitHub Folder: https://github.com/kirstenlynn-ops/Portfolio/tree/main\                                  |     |Project%204%3A%20Spotify%20Listening%20History%20Analysis                                               |
|(Contains notebooks, data work cycle, datasets throughout cleaning and feature engineering              |
|Final Static Dashboard: https://kirstenlynn-ops.github.io/Portfolio/images/Spotify_Static_Dashboard.htm |
|(Final visuals ready for non-technical users 

## Introduction

Streaming platforms collect huge amounts of user interaction data, but most listeners rarely get a deeper look at their own habits. Features like _Spotify Wrapped_ are fun and informative, yet they often overlook deeper, time-driven patterns and behavioral insights.

This project analyzes Spotify listening history from two consenting individuals to explore how listening behavior, genre preferences, and audio related charcteristics vary over time. By comparing patterns between users with different listening styles, this project demonstrated how small-scale behavioral data canbe analyzed responsibly and ethically.

---
## 🎯 Project Goals
- Compare listening behavior between two users woth distinct listening styles
- Identify temporal trends in listening behavior across users
(time of day, day of week, seasonal patterns)
- Examine differences in music consumption volume and consistency
- Analyze how audio features differ by:
     - Time of day
     - Listening context
     - User
- Identify habitual vs exploratory listening behaviors
- Demonstrate ethical handling of personal behavioral data
---
## 🔍 Research Questions & Hypotheses
- **Research Question 1:**
How do listening patterns differ between two users across time?

Hypothesis 1:
One user will demonstarte more consistent listening patterns across time of day and days of the week, while the other will show higher variability and irregual listening sessions.


- **Research Question 2:**
Do users exhibit distinct listening style patterns based on track and artist repetition, skip behavior, and shuffle usage?

Hypothesis 2:
One user (potentially User A) will show more habitual listening behavior (repeated tracks/artists, less skipping, more consistent shuffle usage), while the other (potentially User B) will show more exploratory listening (more variety, higher skip rates, less consistent shuffle usage).


- **Research Question 3:**
How does listening volumn reflect engagement styles?

Hypothesis 3:
One user will show higher overall listening volumn with longer sessions, while the other will exhibit shorter, more frequent listening events.


- **Research Question 4:**
How does listening behavior evolve over time within each user?

Hypothesis 4:
Over time, each user tends to listen to a more consistent set of artists and genres rather than frequently changing their listening style.

---
## 🛠 Project Workflow
|Stage (Notebook)   | Description|
|-------------------|---------------------------------------------------------     |
| NB 0              | Data ingestion & raw data inspection (User A & User B)       |
| NB 1              | Initial exploratory data analysis (EDA) & data cleaning      |
| NB 1b             | Subsequent exploratory analysis                              |
| NB 2              | Feature engineering                                          |
| NB 3              | Behavioral analysis & insight-driven visualizations          |
|Dashboard          |Summary and visual exploration                                |
|Final Write-Up     | Spotify Listening History Analysis (2022–2025)               |

---
## 📊 Data Source
- Spotify – Download Your Data
- Data retrieved via Spotify’s official privacy portal:
https://www.spotify.com/account/privacy/
---
## 🔐 Ethical Considerations & Privacy

This project uses Spotify listening history from two consenting individuals. Both participated voluntarily proved their data for analysis and are aware of how the data is being used.

Privacy and ethical safeguards include:

- Removal of personally identifying information such as IP addresses, usernames, and device identifiers
- Tracks are analyzed strictly as behavioral data points, not endorsements of lyrical content
- Explicit tracks are included only as part of authentic listening history
- Spotify is credited as the original data source

**Note:**
Some tracks are labeled as explicit and may reference adult themes such as violence, substance use, or mature subject matter.
