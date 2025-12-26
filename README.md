# Thesis — LIDAR & Point‑Cloud Projection (Part I)

This repo holds the first part of my master’s thesis: sensor calibration, LiDAR point‑cloud processing and projection of 3D points onto camera images. Parts II and III focused on CNN‑based detection and classification (separate work).

Summary
- Goal: transform raw LiDAR + orientation logs into aligned camera projections and mapping artifacts.
- Approach: read/sample LAS point clouds, apply extrinsic/intrinsic calibrations, project points to image plane, produce visualization and dataset prep for downstream tasks.

What you'll find here (short)
- calibration/, calibration2/ — intrinsic/extrinsic config files
- point_projection.py, projection_utils.py — core projection maths and transforms
- pc_projection_test.py, bbox_projection_test.py — test/example scripts
- las_reader.py, las_plotter.py — LAS ingestion and visualization code
- detactions_preparation.py — dataset/annotation preparation steps
- dati_mappa*.csv, rilevamenti*.txt — raw data / logs used in experiments
- test_single_photo*.py, test.jpg — small examples for sanity checks

Tech & patterns (observed)
- Python tooling: numpy, scipy (Rotation), pandas, matplotlib, laspy, numba, geopy
- File‑based datasets (LAS, CSV, text logs), calibration via config files under ./calibration
- Emphasis on numeric correctness of transforms and reproducible artifacts rather than packaged tooling

For reviewers: look at point_projection.py and projection_utils.py first to evaluate transform correctness; check test scripts for pipeline usage and las_reader.py for data ingestion choices.

Author
- @daniele96l

Notes
- Some scripts reference absolute paths or large LAS files — paths need adapting to run locally.
- Parts II & III (CNN detection/classification) are not included here; I can add links or a short appendix if desired.
