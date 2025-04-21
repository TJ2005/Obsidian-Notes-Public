The **Million Song Dataset (MSD)** contains a variety of metadata and audio features for **1 million** songs. The dataset is structured into multiple files, with the main dataset stored in **HDF5 format**. Here’s a breakdown of the important columns:

---

### **1. Metadata**

| Column Name   | Description                      | Example                |
| ------------- | -------------------------------- | ---------------------- |
| `song_id`     | Unique identifier for a song     | `SOQHXMF12A6D4FD69A`   |
| `title`       | Song title                       | _Bohemian Rhapsody_    |
| `artist_id`   | Unique identifier for the artist | `ARJ7KF01187FB3F5F1`   |
| `artist_name` | Name of the artist               | _Queen_                |
| `release`     | Album or single name             | _A Night at the Opera_ |
| `year`        | Release year                     | `1975`                 |
| `duration`    | Length of the song in seconds    | `355.47`               |
| `track_id`    | MusicBrainz Track ID             | `TRMMMYQ128F932D901`   |

---

### **2. Audio Features**

|Column Name|Description|Example|
|---|---|---|
|`tempo`|BPM (beats per minute)|`120.5`|
|`key`|Musical key (0 = C, 1 = C#, ..., 11 = B)|`5` (F Major)|
|`mode`|1 = Major, 0 = Minor|`1`|
|`time_signature`|Time signature (3, 4, or 5)|`4` (4/4 time)|
|`loudness`|Overall loudness in dB|`-5.5`|
|`danceability`|A measure of how danceable a song is (0-1)|`0.8`|
|`energy`|Energy level of the track (0-1)|`0.9`|

---

### **3. Genre & Similarity**

|Column Name|Description|Example|
|---|---|---|
|`artist_terms`|List of genre tags|`['rock', 'classic rock']`|
|`artist_familiarity`|Popularity score (0-1)|`0.85`|
|`artist_hotttnesss`|Hotness score (0-1)|`0.9`|
|`similar_artists`|List of similar artists' IDs|`['AR1', 'AR2', 'AR3']`|

---

### **4. Additional Features (Segment-Level Analysis)**

These are detailed audio features analyzed per second for deeper audio processing:

- **MFCCs (Mel-Frequency Cepstral Coefficients)** – Used in audio signal processing
- **Pitch & Timbre Features** – For sound quality analysis

---


# Roadmap
- http://labrosa.ee.columbia.edu/~dpwe/tmp/millionsongsubset.tar.gz Download this first
- Wait for AWS Authentication
- 