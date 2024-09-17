# SST Grade Engine

## Aim

This project will expose an API and user interface to which will accept student data and output a correct result for each student based on user defined metrics and weightage for score calulation.

## Application Design

This project will contain a single class called the `GradeEngine`. This class will take some metadata about the result to be calculated as input and output a sorted array of objects consisting of details of students performance.

```
GradeEngine(PerformanceData: Dataframe, Metrics: DataFrame) -> sorted listof StudentData 
```

## Tech Stack

The logic will be written purely in Python and will be served using a FastAPI server, with the following endpoints:-

```
GET /data

Fetches the ID of all the data files(csv) available to be graded.

POST /data

Uploads a given csv file into the server for grade calculation.

DELETE /data/<dataID>

Deletes the file with ID from the server.

POST /data/<dataID>/metric

Adds a grading metric(csv) to the data with ID `dataID`.
```

