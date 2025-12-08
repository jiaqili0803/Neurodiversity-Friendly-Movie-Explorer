# Neurodiversity-Friendly-Movie-Explorer

This web-based visualization prototype is designed to support neurodiverse users, especially people with characteristics related to ADHD.
It presents an interactive movie similarity network based on the MovieLens dataset, using visual encodings and interaction patterns that reduce cognitive overload and support exploratory browsing.
This tool is deployed on Render as a web application where users can search, explore, zoom, and interpret relationships among movies based on genres, user-generated tags, and audience engagement levels.

## Live Demo (Render Deployment)
🔗 [https://neurodiversity-friendly-movie-explorer.onrender.com]
(If the free Render service is “waking up,” it may take several seconds to load)

## Features
1. Two Visualization Modes
Simple Mode – Calm View
Rich Mode – Deep Dive
2. Interactive Components
Hover (Details-on-Demand)
Click (Recenter + Focus Lock)
Helps avoid accidental disorientation (ADHD-friendly)
Search (Brushing & Linking)
Highlights the searched movie with an orange halo
Reset View
Linked Histogram

## Design Principles
Reduced visual clutter (simple mode)
Clear visual hierarchy
Consistent color meanings
Smooth transitions to avoid sudden or overwhelming changes
High readability legends and interaction instructions
Background context retained so users never feel “lost”

* Running Locally
** Install requirements
    pip install -r requirements.txt
** Run the Dash app
    python app.py

* Deploying on Render (Web-Based)
** Push this project to GitHub
** On Render → New Web Service → select your repo
** Use these settings:
    Build Command
    pip install -r requirements.txt
    Start Command
    gunicorn app:server
** Render will auto-deploy your Dash web app and provide a sharable URL.

## Data Processing Summary
The raw MovieLens dataset was transformed into a network-friendly format:
Nodes (network_nodes.csv) include:
movieId
title
genres + main genre
audience engagement (rating counts)
normalized marker sizes
average rating
spring-layout coordinates
top user-generated tags (from tags.csv)
Edges (network_edges.csv) include:
movieId source
movieId target
similarity scoreComputed based on:
shared genres
shared user-generated tags
(optional) weighted combination rules
Rating histogram (rating_hist.csv)
Pre-aggregated rating distributions
Used for brushing & linking

## Dataset License & Required Citation
This project uses the MovieLens 25M Dataset by GroupLens Research at the University of Minnesota.
Although the data is processed and transformed for visualization purposes, the original dataset is copyrighted and must be cited according to its license.

### Usage License Summary (from MovieLens)
The MovieLens dataset may be used for research purposes under conditions including:
You must not imply endorsement from the University of Minnesota or the GroupLens Research Group.
You must acknowledge and cite MovieLens in any publications or projects using the data.
Data (including transformed versions) may be redistributed only under the same license terms.
The dataset may not be used commercially without permission from GroupLens.
All dataset files are provided “as is” with no warranty.
GroupLens and the University of Minnesota are not liable for damages resulting from use of the dataset.

#### Required Citation
If you use this project or dataset in an academic setting, cite the official MovieLens dataset publication:

_F. Maxwell Harper and Joseph A. Konstan. 2015.
The MovieLens Datasets: History and Context.
ACM Transactions on Interactive Intelligent Systems (TiiS) 5, 4 (2015), 19:1–19:19.
DOI: https://doi.org/10.1145/2827872_

#### About MovieLens / GroupLens
GroupLens is a research group at the University of Minnesota focusing on:
recommender systems
online community behavior
social computing
digital libraries
ubiquitous computing
MovieLens provides the movie recommendation platform from which this dataset originates. Visit: https://movielens.org

## Acknowledgment
This visualization project does not claim ownership of the MovieLens dataset.
All data originates from MovieLens and is used respectfully in accordance with its research license.
Only cleaned, aggregated, and transformed versions of the data appear in the app.
