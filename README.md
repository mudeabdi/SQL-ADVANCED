# SQL Practice Dataset: Music Streaming Analytics

## Overview
This dataset contains comprehensive music streaming data from various platforms (Spotify, YouTube) with detailed track information, artist data, and performance metrics. It's designed for SQL practice exercises ranging from basic queries to advanced analytical operations.

## Dataset Information

**File:** `cleaned_final.csv`  
**Records:** 20,000+ tracks  
**Format:** CSV (Comma-Separated Values)

## Column Descriptions

| Column Name | Data Type | Description |
|------------|-----------|-------------|
| `Artist` | VARCHAR | Name of the artist or band |
| `Track` | VARCHAR | Name of the song/track |
| `Album` | VARCHAR | Album name containing the track |
| `Album_type` | VARCHAR | Type of album (album, single, compilation) |
| `Danceability` | FLOAT | How suitable the track is for dancing (0.0 to 1.0) |
| `Energy` | FLOAT | Intensity and activity measure (0.0 to 1.0) |
| `Loudness` | FLOAT | Overall loudness in decibels (dB) |
| `Speechiness` | FLOAT | Presence of spoken words in track (0.0 to 1.0) |
| `Acousticness` | FLOAT | Confidence measure of acoustic sound (0.0 to 1.0) |
| `Instrumentalness` | FLOAT | Predicts if track contains no vocals (0.0 to 1.0) |
| `Liveness` | FLOAT | Presence of audience in recording (0.0 to 1.0) |
| `Valence` | FLOAT | Musical positiveness/happiness (0.0 to 1.0) |
| `Tempo` | FLOAT | Beats per minute (BPM) |
| `Duration_min` | FLOAT | Track duration in minutes |
| `Title` | VARCHAR | Full title with artist attribution |
| `Channel` | VARCHAR | YouTube channel name |
| `Views` | BIGINT | Total YouTube views |
| `Likes` | BIGINT | Total YouTube likes |
| `Comments` | INTEGER | Total YouTube comments |
| `Licensed` | BOOLEAN | Whether the content is licensed (TRUE/FALSE) |
| `official_video` | BOOLEAN | Whether it's an official music video (TRUE/FALSE) |
| `Stream` | BIGINT | Total streams on Spotify |
| `EnergyLiveness` | FLOAT | Calculated ratio of Energy to Liveness |
| `most_playedon` | VARCHAR | Platform with most plays (Spotify/YouTube) |

## Setup Instructions

### 1. Create Database and Table

```sql
-- Create database
CREATE DATABASE music_streaming;
USE music_streaming;

-- Create table
CREATE TABLE tracks (
    Artist VARCHAR(255),
    Track VARCHAR(255),
    Album VARCHAR(255),
    Album_type VARCHAR(50),
    Danceability FLOAT,
    Energy FLOAT,
    Loudness FLOAT,
    Speechiness FLOAT,
    Acousticness FLOAT,
    Instrumentalness FLOAT,
    Liveness FLOAT,
    Valence FLOAT,
    Tempo FLOAT,
    Duration_min FLOAT,
    Title VARCHAR(500),
    Channel VARCHAR(255),
    Views BIGINT,
    Likes BIGINT,
    Comments INT,
    Licensed BOOLEAN,
    official_video BOOLEAN,
    Stream BIGINT,
    EnergyLiveness FLOAT,
    most_playedon VARCHAR(50)
);
```

---

## SQL Practice Questions

### 📊 Easy Level

#### 1. High-Performing Tracks
Retrieve the names of all tracks that have more than 1 billion streams.

**Learning Objectives:** Basic SELECT, WHERE clause, numeric comparisons

---

#### 2. Album-Artist Listing
List all albums along with their respective artists.

**Learning Objectives:** SELECT with multiple columns, DISTINCT usage

---

#### 3. Licensed Track Engagement
Get the total number of comments for tracks where `licensed = TRUE`.

**Learning Objectives:** Aggregate functions (SUM/COUNT), filtering with boolean

---

#### 4. Single Album Filter
Find all tracks that belong to the album type "single".

**Learning Objectives:** String filtering, equality operations

---

#### 5. Track Count by Artist
Count the total number of tracks by each artist.

**Learning Objectives:** GROUP BY, COUNT function, aggregation basics

---

### 📈 Medium Level

#### 6. Average Danceability per Album
Calculate the average danceability of tracks in each album.

**Learning Objectives:** AVG function, GROUP BY with multiple columns

---

#### 7. Top Energy Tracks
Find the top 5 tracks with the highest energy values.

**Learning Objectives:** ORDER BY, LIMIT/TOP, descending sort

---

#### 8. Official Video Metrics
List all tracks along with their views and likes where `official_video = TRUE`.

**Learning Objectives:** Multiple column selection, boolean filtering

---

#### 9. Total Views per Album
For each album, calculate the total views of all associated tracks.

**Learning Objectives:** SUM with GROUP BY, aggregation

---

#### 10. Platform Comparison
Retrieve the track names that have been streamed on Spotify more than YouTube.

**Learning Objectives:** Comparison between columns, conditional filtering

---

### 🚀 Advanced Level

#### 11. Top 3 Viewed Tracks per Artist
Find the top 3 most-viewed tracks for each artist using window functions.

**Learning Objectives:** Window functions, ROW_NUMBER(), PARTITION BY

---

#### 12. Above-Average Liveness
Write a query to find tracks where the liveness score is above the average.

**Learning Objectives:** Subqueries, aggregate functions in WHERE clause

---

#### 13. Energy Range per Album
Use a WITH clause to calculate the difference between the highest and lowest energy values for tracks in each album.

**Learning Objectives:** Common Table Expressions (CTE), MAX/MIN functions

---

#### 14. Energy-to-Liveness Ratio Filter
Find tracks where the energy-to-liveness ratio is greater than 1.2.

**Learning Objectives:** Calculated columns, division operations, NULL handling

---

#### 15. Cumulative Likes by Views
Calculate the cumulative sum of likes for tracks ordered by the number of views, using window functions.

**Learning Objectives:** Window functions, SUM() OVER(), ORDER BY in windows

## Additional Challenge Questions

### 🎯 Bonus Challenges

1. **Multi-Platform Success:** Find artists who have at least one track with 1B+ streams AND 500M+ views

2. **Genre Energy Analysis:** Calculate the average energy, danceability, and valence for each artist

3. **Engagement Rate:** Create a calculated column for engagement rate: `(Likes + Comments) / Views * 100`

4. **Duration Categories:** Categorize tracks into "Short" (<3 min), "Medium" (3-5 min), and "Long" (>5 min) and count each category

5. **Year-over-Year Growth:** If you have multiple snapshots of this data, calculate growth rates for views and streams

---

