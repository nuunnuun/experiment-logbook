# UWB Localization Logbook

## Overview

A full-stack web application for recording and comparing indoor UWB
localization experiments before integrating the system with a drone.

The application will help users compare estimated positions against
ground-truth positions and evaluate how changes to anchor layouts
and processing methods affect positioning accuracy.

## Intended Users

Students and anyone interested in testing and evaluating UWB
localization systems.

## Planned Features

- Create and manage experiments.
- Record the anchor coordinates used in each experiment.
- Add, view, edit, and delete position samples.
- Calculate the positioning error for each sample.
- Display the mean error, maximum error, and percentage of samples
  within the target threshold.
- Compare results between experiments.

The initial version will use manually entered or clearly labeled
simulated data. Hardware integration and Kalman filtering are planned
for later stages.

## Initial Data

### Experiment Information

- Experiment name and description
- Anchor IDs and their x, y, z coordinates
- Processing method, such as raw or filtered
- Data source, such as simulated or measured

### Position Samples

- Timestamp
- Ground-truth position: x, y, z
- Estimated position: x, y, z

All coordinates will use meters and the same coordinate system.
Errors may also be displayed in centimeters.

## Accuracy Evaluation

Positioning error will be calculated as the 3D Euclidean distance
between the estimated position and the ground-truth position:

error = sqrt(
    (estimated_x - true_x)^2 +
    (estimated_y - true_y)^2 +
    (estimated_z - true_z)^2
)

The initial target is an error of no more than 0.01 meters (1 cm)
for each sample.

The application will report whether recorded samples meet this target.
It does not guarantee that the UWB hardware can achieve this accuracy.

The evaluation criterion will be confirmed with the project supervisor.

## Planned Tech Stack

- HTML — page structure
- CSS — page styling
- JavaScript — browser interactions and API requests
- Python / FastAPI — backend API and calculations
- PostgreSQL — data storage
- Docker Compose — running backend and database services
- DBeaver — inspecting the database during development
- Git / GitHub — version control and project sharing

## Project Status

Planning stage.

The project scope and initial data requirements have been defined.
The frontend, backend, database, and hardware integration have
not yet been implemented.