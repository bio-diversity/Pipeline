# Pipeline
A full pipeline from audio data to acoustic graphs


## Continuous Ecological Monitoring using bioacoustics sensing in Sanjay Van

This project is an initiative for continuous ecological monitoring in Sanjay Van, Delhi, using bioacoustics sensing. The core idea is to deploy automated acoustic recorders in the forest to capture the soundscape over long periods. By analyzing this rich sound data, we can gain insights into biodiversity, ecosystem health, and the daily and seasonal behaviors of species without the need for constant on-site human presence. This project was conducted by the CoRE stack team at IIT Delhi in August 2025.

### Inputs
The project's primary data inputs are raw audio recordings and location-specific metadata.

### Acoustic Data Collection

Recording Device: We used Song Meter Micro 2 devices to capture high-quality audio.

Duty Cycle: The devices were programmed with a 2:4 duty cycle, meaning they recorded audio for 2 minutes and then entered a "sleep" mode for 4 minutes to conserve battery life. This continuous sampling was carried out over a two-week period, from July 20 to August 3, 2025.

Site Selection: Four distinct monitoring spots were selected within Sanjay Van. The sites were chosen after stratifying the forest into four different regions using spectral data, specifically NDVI time series, to ensure we covered a variety of habitat types.

### Monitoring Spot Characteristics

Each of the four selected sites had unique characteristics that would influence the local soundscape:

Spot 1: A dense area with diverse deciduous trees, located close to a stream.

Spot 2: Positioned at a higher elevation, approximately 100 meters away from a waterbody.

Spot 3: A region dominated by acacia trees and with a noticeable presence of lantana and crickets.

Spot 4: A site located near a new growth area with many young trees.

### Outputs and Analysis
The project outputs are a series of analyses and data visualizations that help interpret the soundscape data. The analysis is divided into two main categories: species-level analysis and soundscape-level analysis using acoustic indices.

### Species-Level Analysis

- BirdNet Identifications: The audio files are processed using the BirdNet model to automatically identify bird species. The reliability of these identifications is assessed using a confusion matrix based on an eBird species list for the region. The analysis categorizes species into:

- Confirmed Present (True Positives): Species found on both the eBird list and BirdNet detections.

- Confirmed Absent/Missed (False Negatives): Species on the eBird list but not detected by BirdNet.

- Implausible Errors (False Positives): Species found by BirdNet but not on the eBird list and considered impossible for the region.

- Hourly Activity Heat Maps:

  - Normalized Heat Maps: These maps show the proportion of a species' total daily activity per hour. The data is normalized for each species, allowing for a fair comparison of activity timing regardless of how common or vocal a species is.<img width="1004" height="508" alt="Screenshot 2025-09-13 at 5 20 41 AM" src="https://github.com/user-attachments/assets/88aa3bbe-fcb4-4783-98aa-2d35251368c5" />


  - Non-Normalized Heat Maps: These heat maps display the raw average number of detections per hour for each species. They are crucial for identifying which species contribute the most to the overall soundscape at any given time.
<img width="1004" height="508" alt="Screenshot 2025-09-13 at 5 21 56 AM" src="https://github.com/user-attachments/assets/5e207d86-8a56-4978-86f7-bac5f427e084" />


- "Stickiness" Metrics: These metrics quantify the predictability of species' behavior.

  - Temporal Stickiness: Measures the regularity of a species' daily activity pattern across consecutive days using a Spearman rank correlation of hourly detection counts. A high score indicates a predictable schedule.<img width="597" height="483" alt="Screenshot 2025-09-13 at 5 24 23 AM" src="https://github.com/user-attachments/assets/cfb1a41e-a482-4064-8247-45c0c5e07c52" />



  - Spatial Stickiness: Measures a species' affinity for a specific location. It's calculated by comparing the spot ranking (based on detection counts) from one day to the next.
  
<img width="525" height="581" alt="Screenshot 2025-09-13 at 5 23 47 AM" src="https://github.com/user-attachments/assets/2dbce094-8a00-4e7f-b6aa-86f409ca6b3e" />


  - Temporal-Spatial Stickiness: A combined metric that assesses the predictability of a species' hourly activity at a specific spot across multiple days.
<img width="597" height="483" alt="Screenshot 2025-09-13 at 5 24 43 AM" src="https://github.com/user-attachments/assets/e514a1ac-663c-4ba4-b19a-0781269acc74" />

### Soundscape-Level Analysis (Acoustic Indices)

Acoustic indices are single-value metrics that provide a broad, rapid assessment of the soundscape's characteristics. The following indices were computed hourly for each location:

- Acoustic Diversity Index (ADI): Measures how evenly sound energy is distributed across frequency bands. A high ADI suggests a rich and healthy ecosystem with a wide variety of vocalizing species.
- Acoustic Complexity Index (ACI): Measures rapid variations in sound intensity over time. High ACI often correlates with a complex biological soundscape.
- Acoustic Evenness Index (AEI): Evaluates whether acoustic energy is evenly distributed or concentrated in a few frequency bands. A high AEI indicates a balanced soundscape.
 
- Normalized Difference Soundscape Index (NDSI): Compares biological sound energy (E_Bio) to human-made noise energy (E_Anthro) in different frequency ranges.

- Mid Frequency Cover (MFC): Measures the proportion of the soundscape with a strong mid-frequency signal, which is typically a signature of birds and insects.

- Clustered Level of Sound (CLS): Assesses the balance of energy among different frequency clusters. A high CLS indicates a diverse set of sound sources.<img width="1048" height="417" alt="Screenshot 2025-09-13 at 5 30 12 AM" src="https://github.com/user-attachments/assets/c96643b9-2f72-4597-ab42-551d13cc288d" />

