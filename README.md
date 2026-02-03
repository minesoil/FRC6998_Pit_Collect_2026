FRC 6998 Pit Collect Tool (2026)

This is a standalone, offline-capable web application for collecting Pit Scouting data and Autonomous Paths for the FRC 2026 game. It generates compressed QR codes that can be scanned by the main Scouting App to upload data without needing an internet connection in the pits.

Features

Offline First: Does not require internet to generate QR codes.

Data Compression: Uses LZ-String to compress data into dense QR codes.

Auto Path Drawing: Allows scouters to draw multiple autonomous paths on a visual field map.

Multi-QR Generation: Generates separate QR codes for robot data and each autonomous path drawn.

Validation: Includes profanity filters and logical checks (e.g., Preload cannot exceed Capacity).

Setup Guide

Requirements

A modern web browser (Chrome, Safari, Firefox).

A device with a touchscreen (tablet/iPad preferred) for drawing paths.

Files Needed

Ensure these files are in the same folder:

index.html (The main application code)

field_2026.png (Top-down view of the 2026 Field)

Installation

Simply open index.html in your web browser. No server or installation is required.

How to Use

Step 1 (ID): Enter name and team number.

Step 2-3 (Specs): Enter robot weight and hardware details.

Step 4 (Auto): Check boxes for auto capabilities.

Step 5 (Teleop): Enter climb and endgame details.

Step 6 (Review): Click "Generate Data QR". Scan this with the Scanner App.

Step 7 (Path): Click "Next: Draw Auto Path".

Draw lines for the auto routine.

Lift finger to start a new path.

Click "Generate Path QRs" and scan them individually.

Data Schemas

Robot Data QR (22 Columns)

Format: TSV (Tab Separated Values) -> Compressed Base64

Index  Field          Description
0      Team Number    e.g., 6998
1      Scouter Name   Name of person scouting
2      Chassis        Swerve, Tank, etc.
3      Weight         lbs
...    ...            ...
21     Notes          Text notes

Path QR (4 Columns)

Format: TSV -> Compressed Base64

Index  Field         Value
0      Event Code    2026PIT
1      Match Number  0 (Constant for Pit)
2      Team Number   e.g., 6998
3      Path Data     x1,y1

Future Features

Photo Capture: Camera integration for robot photos.

Blue Alliance Integration: Fetch team avatars.

Local Storage History: Save progress locally to prevent data loss.

Dark Mode: Theming for different lighting conditions.