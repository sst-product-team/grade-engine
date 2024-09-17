# SST Grade Engine

## Aim

This project will expose an API and user interface to which will accept student data and output a correct result for each student based on user defined metrics and weightage for score calulation.

## Application Design

This project will contain a single class called the `GradeEngine`. This class will take some metadata about the result to be calculated as input and output a sorted array of objects consisting of details of students performance.

```
GradeEngine(PerformanceData: Dataframe, Metrics: DataFrame) -> sorted listof StudentData 
```

## Tech Stack & API Specifications

The frontend will be written React and the logic will be written purely in Python and will be served using a FastAPI server, with the following endpoints:-

```
GET /data

Fetches the ID of all the data files(csv) available to be graded.
```
```
POST /data

Uploads a given csv file into the server for grade calculation.
{
  "filename": stiring,
  "file": file
}
```
```
DELETE /data/<dataID>

Deletes the file with ID from the server.
```
```
POST /data/<dataID>/metric

Adds a grading metric(csv) to the data with ID `dataID`.
{
  "metricName": string,
  "metrics": object
}
```
```
GET /grade/<dataID>/<metricID>

Calculates and returns the grades of students based on student data with ID `dataID` and metric `metricID`
```

## v1 Scope

- For every `StudentData` sheet we will store an aggregation column.
- Automatic email handling to students

## v2 Scope

- Implement custom logic on columns which is triggered when certian criteria are not fulfilled by a result of a student like attendance below 75% when CGPA is not above 9.0, reduce the final result of the student by some formula.
