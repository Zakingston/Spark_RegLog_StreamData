# Spark_RegLog_StreamData
Logistic Regression with a stream of simulated data (airlines) from 20 csv files with Spark. 


## Phases of the Project
Phase 1: Preparation of the Logistic Regression ML Model.

Reuse the Logistic Regression model proposed in Sprint 3 as the initial step for the streaming phase.

Phase 2: Data Preparation

The original file survey_airline.csv must be divided into 20 equal parts using the repartition() method, and the parts of the file must be saved in a directory that will constitute the data stream source.

The stream source directory must be completely deleted with each stream execution for the simulation to function correctly. The source data directory must always be as follows: dbfs:/FileStore/tables/project/streaming/

Phase 3: Creation of the Streaming Source

Create the data source for the stream with the readStream() method and the required parameters for its correct implementation.

Apply the transform() method on the generated model, passing the previously created source stream as a parameter, and visualize the resulting data stream with the display() method.

Phase 4: Implementation of an Additional Query

Create a second query on the resulting stream from the previous step using the writeStream() method with an "append" output mode, "memory" format, and name "surveyClassification".

Phase 5: Evaluation of the Streaming Model

Create a MulticlassClassificationEvaluator object to obtain the "accuracy" metric.

From the "surveyClassification" query, generate a DataFrame using spark.sql() and pass this resulting DataFrame as a parameter to the evaluator using the evaluate() method.

Finally, print the resulting "accuracy" metric for the model.
