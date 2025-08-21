# Boat Noise Alters Behaviour in a Fish-Shrimp Mutualism  

## Overview  

This repository contains data and code for a field experiment investigating how boat noise from different engine types (**2-stroke** and **4-stroke**) affects the mutualistic partnership between **Steinitz’s goby** (*Amblyeleotris steinitzi*) and **snapping shrimp** (*Alpheus* spp.).  

The data was collected between 25 October and 25 November 2017 at Lizard Island (14°41'9"S, 145°27'21"E) on the Great Barrier Reef, Australia.

##### Associated pre-print (to be updated onced published): 
Manera J.L., Martin J.M., Palacios M.M., Mason R.T., McCormick M.I., Wong B.B.M. (2025) Boat noise alters behaviour in a fish-shrimp mutualism. *Authorea*. [DOI: 10.22541/au.175068258.87978389/v1](https://doi.org/10.22541/au.175068258.87978389/v1)

##### Contact:
Jack L. Manera – [jack.manera@monash.edu](mailto:jack.manera@monash.edu)

##### Repository links:
- [GitHub](https://github.com/JLManera/shrimp_goby_boatnoise)
- [OSF](https://osf.io/3x5yf/?view_only=dff0b2d2661142f7bab5e4d69cdbd75a)

##### Licencing:
CC BY-NC-SA 4.0 - [Attribution-NonCommercial-ShareAlike 4.0 International](https://creativecommons.org/licenses/by-nc-sa/4.0/)

## Running the Code  

1. **Download** this repository while maintaining the same folder structure.  
2. **Open** `shrimp-goby-boatnoise.Rproj` in **RStudio** (or another R-compatible interface).  
3. **Run** the code as instructed in the `ms_boatnoise_shrimp_goby.rmd`. Thorough annotations are included in the script for further clarification.  

## Folder & File Structure  

### **1-data/** _(Contains all processed and raw data)_  
- **`BORIS_output.csv`** – Raw output from the behaviour logging software **BORIS**.  
- **`final_df.csv`** – Cleaned and wrangled dataframe used for analysis.  
- **`species.csv`** – A table specifying which shrimp species were present in each blinded video.  
- **`Video_codes.csv`** – Video coding information used for blind data extraction, including treatment details and metadata.  

### **3-models/** _(Contains saved models)_  

### **Project Files**  
- **`shrimp-goby-boatnoise.Rproj`** – R project file for easy navigation and execution in **RStudio**.  
- **`ms_boatnoise_shrimp_goby.rmd`** – R script for data wrangling, analysis, and visualization using **brms** models. 

## Data documentation

### 1. BORIS_output.csv

This file contains detailed records of individual animal behaviours during experimental trials recorded using the manual behaviour logging software **BORIS**.

Columns:

- **subject** – The taxon and identifying number of the animal in the video frame. This ID is unique within a video but not across trials.
- **behaviour** – The specific behaviour observed, with possible values:
  - **INSIDE** – Animal is inside the burrow.
  - **EDGE** – Part of the animal's body is inside and part is outside of the burrow entrance.
  - **NEAR** – Animal is within one body length of the burrow entrance but completely out of the burrow.
  - **AWAY** – Animal is more than one body length away from the burrow entrance.
  - **CONTACT** – Shrimp is within one body length of a goby.
  - **APART** – Shrimp is more than one body length away from the goby.
  - **EAT** – Feeding behaviour observed.
  - **DEFENCE** – Goby performs a defensive action toward a conspecific.
  - **DASH** – Animal rapidly retreats into its burrow.
  - **OUT OF FRAME** – Animal moves out of the video frame.
  - **BLACK EYES** – Goby’s eyes turn black, likely as a visual signal.
  - **CHASE HETEROSPECIFIC** – Goby chases a different species.
  - **CHASE CONSPECIFIC** – Goby chases another goby that is not sharing the same burrow.
  - **CHASE UNKNOWN** – Goby chases an unknown animal (out of frame).
- **count** – Number of times the behaviour was observed.
- **total_duration_s** – Cumulative duration of the behaviour (in seconds).
- **video_id** – Unique code name for the video, assigned to maintain blinding.

### 2. final_df.csv

This file contains summary-level data for each experimental trial, including burrow conditions, species counts, and experimental treatments.

Columns:

- **burrow** – Unique identifier for each burrow.
- **stage** – Experimental phase relative to noise exposure: pre-treatment, during-treatment, or post-treatment.
- **boat_id** – Identifier for the boat used in noise treatments.
- **stroke** – The type of boat engine: 4-stroke, 2-stroke, or control (no boat noise).
- **site** – Sampling site within the Lizard Island lagoon.
- **goby_number** – Number of gobies observed at the burrow.
- **shrimp_species** – The species of snapping shrimp observed.
- **goby_total** – The total time recorded for all goby behvaiours in the trial averaged over the number of gobies present.
- **goby_out** – The amount of time gobies spent outside the burrow (averaged across the number of gobies).
- **burrow_stage** – Developmental stage or condition of the burrow.
- **shrimp_out** – The amount of time shrimp spent outside the burrow (averaged across the number of shrimp).
- **shrimp_total** – The total time recorded for all shrimp behvaiours in the trial averaged over the number of shrmip present.
- **shrimp_number** – Number of shrimp present in the burrow.
- **shrimp_contact** – The total time shrimp spent in within one body length of a goby, the proxy for contact.

### 3. species.csv

This file links shrimp species to their corresponding video codes.

Columns:

- **species** – The species of snapping shrimp observed in this burrow.
- **code** – Unique code name for the video, assigned to maintain blinding.

### 4. Video_codes.csv

This file provides metadata on the experimental setup and links video codes to their respective trial conditions. 

Columns:

- **date_file** – The date of the experiment and the boat order for that day (indicated by a letter).
- **video_section** – The phase of the noise treatment (pre-treatment, during-treatment, post-treatment).
- **code** – Unique code name for the video, assigned to maintain blinding.
- **site** – Sampling site within the Lizard Island lagoon.
- **boat_name** – The unique name of the boat used in the trial.
- **stroke** – The engine type (4-stroke, 2-stroke, or control).
- **cum_sum_boat_trials_per_site** – The cumulative count of the number of boat noise treatments (both 4- and 2-stroke) that had been run at that sample site over the course of the entire experimental period.

## Funding

This work was supported by an ARC Discovery (MIM; DP170103372) and an Alfred Deakin Postdoctoral Research Fellowship (JMM).






