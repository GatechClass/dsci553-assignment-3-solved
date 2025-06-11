# dsci553-assignment-3-solved
**TO GET THIS SOLUTION VISIT:** [DSCI553 Assignment 3 Solved](https://mantutor.com/product/dsci553-foundations-and-applications-of-data-mining-solved-3/)


---

**For Custom/Order Solutions:** **Email:** mantutorcodes@gmail.com  

*We deliver quick, professional, and affordable assignment help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;114963&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;3&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (3 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;DSCI553 Assignment 3 Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (3 votes)    </div>
    </div>
&nbsp;

1. Overview of the Assignment

In Assignment 3, you will complete two tasks. The goal is to familiarize you with Locality Sensitive Hashing (LSH), and different types of collaborative-filtering recommendation systems. The dataset you are going to use is a subset from the Yelp dataset used in the previous assignments.

2. Assignment Requirements

2.1 Programming Language and Library Requirements

a. You must use Python to implement all tasks. You can only use standard python libraries (i.e., external libraries like numpy or pandas are not allowed). There will be a 10% bonus for each task (or case) if you also submit a Scala implementation and both your Python and Scala implementations are correct.

b. You are required to only use the Spark RDD to understand Spark operations. You will not receive any points if you use Spark DataFrame or DataSet.

2.2 Programming Environment

Python 3.6, JDK 1.8, Scala 2.12, and Spark 3.1.2

We will use these library versions to compile and test your code. There will be no point if we cannot run your code on Vocareum. On Vocareum, you can call `spark-submit` located at /opt/spark/spark-3.1.2-binhadoop3.2/bin/spark-submit`. (*Do not use the one at `/home/local/spark/latest/bin/spark-submit (2.4.4))

2.3 Write your own code

Do not share your code with other students!!

3. Yelp Data

In this assignment, the datasets you are going to use are from:

https://drive.google.com/drive/folders/1SufecRrgj1yWMOVdERmBBUnqz0EX7ARQ?usp=shar ing

We generated the following two datasets from the original Yelp review dataset with some filters. We randomly took 60% of the data as the training dataset, 20% of the data as the validation dataset, and 20% of the data as the testing dataset.

a. yelp_train.csv: the training data, which only include the columns: user_id, business_id, and stars.

b. yelp_val.csv: the validation data, which are in the same format as training data.

c. We are not sharing the test dataset.

d. other datasets: providing additional information (like the average star or location of a business)

4. Tasks

Note: This Assignment has been divided into 2 parts on Vocareum. This has been done to provide more computational resources.

4.1 Task1: Jaccard based LSH (2 points)

In this task, you will implement the Locality Sensitive Hashing algorithm with Jaccard similarity using yelp_train.csv.

In this task, we focus on the “0 or 1” ratings rather than the actual ratings/stars from the users. Specifically, if a user has rated a business, the user’s contribution in the characteristic matrix is 1. If the user hasn’t rated the business, the contribution is 0. You need to identify similar businesses whose similarity &gt;= 0.5.

You can define any collection of hash functions that you think would result in a consistent permutation of the row entries of the characteristic matrix. Some potential hash functions are: f(x)= (ax + b) % m or f(x) = ((ax + b) % p) % m

where p is any prime number and m is the number of bins. Please carefully design your hash functions.

After you have defined all the hashing functions, you will build the signature matrix. Then you will divide the matrix into b bands with r rows each, where b x r = n (n is the number of hash functions). You should carefully select a good combination of b and r in your implementation (b&gt;1 and r&gt;1). Remember that two items are a candidate pair if their signatures are identical in at least one band.

Your final results will be the candidate pairs whose original Jaccard similarity is &gt;= 0.5. You need to write the final results into a CSV file according to the output format below. Example of Jaccard Similarity:

user1 user2 user3 user4

business1 0 1 1 1

business2 0 1 0 0

Ja ccard Similarity (business1, business2) = #intersection / #union = /3

Input format: (we will use the following command to execute your code)

Python: spark-submit task1.py &lt;input_file_name&gt; &lt;output_file_name&gt;

Scala: spark-submit –class task1 hw3.jar &lt;input_file_name&gt; &lt;output_file_name&gt;

Param: input_file_name: the name of the input file (yelp_train.csv), including the file path. Param: output_file_name: the name of the output CSV file, including the file path. Output format:

IMPORTANT: Please strictly follow the output format since your code will be graded automatically. We will not regrade because of formatting issues.

a. The output file is a CSV file, containing all business pairs you have found. The header is “business_id_1, business_id_2, similarity”. Each pair itself must be in the alphabetical order. The entire file also needs to be in the alphabetical order. There is no requirement for the number of decimals for the similarity value. Please refer to the format in Figure 2.

Figure 2: a CSV output example for task1

Grading:

We will compare your output file against the ground truth file using precision and recall metrics.

Precision = true positives / (true positives + false positives)

Recall = true positives / (true positives + false negatives)

The ground truth file has been provided in the Google drive, named as “pure_jaccard_similarity.csv”. You can use this file to compare your results to the ground truth as well.

The ground truth dataset only contains the business pairs (from the yelp_train.csv) whose Jaccard similarity &gt;=0.5. The business pair itself is sorted in the alphabetical order, so each pair only appears once in the file (i.e., if pair (a, b) is in the dataset, (b, a) will not be there).

In order to get full credit for this task you should have precision &gt;= 0.99 and recall &gt;= 0.97. If not, then you will get only partial credit based on the formula:

(Precision / 0.99) * 0.4 + (Recall / 0.97) * 0.4

Your runtime should be less than 100 seconds. If your runtime is more than or equal to 100 seconds, you will not receive any point for this task.

4.2 Task2: Recommendation System (5 points)

In task 2, you are going to build different types of recommendation systems using the yelp_train.csv to predict the ratings/stars for given user ids and business ids. You can make any improvement to your recommendation system in terms of speed and accuracy. You can use the validation dataset (yelp_val.csv) to evaluate the accuracy of your recommendation systems, but please don’t include it as your training data.

There are two options to evaluate your recommendation systems. You can compare your results to the corresponding ground truth and compute the absolute differences. You can divide the absolute differences into 5 levels and count the number for each level as following:

&gt;=0 and &lt;1: 12345

&gt;=1 and &lt;2: 123

&gt;=2 and &lt;3: 1234

&gt;=3 and &lt;4: 1234

&gt;=4: 12

This means that there are 12345 predictions with &lt; 1 difference from the ground truth. This way you will be able to know the error distribution of your predictions and to improve the performance of your recommendation systems.

Additionally, you can compute the RMSE (Root Mean Squared Error) by using following formula:

Where Predi is the prediction for business i and Ratei is the true rating for business i. n is the total number of the business you are predicting.

In this task, you are required to implement:

Case 1: Item-based CF recommendation system with Pearson similarity (2 points)

Case 2: Model-based recommendation system (1 point)

Case 3: Hybrid recommendation system (2 point)

4.2.1. Item-based CF recommendation system

Please strictly follow the slides to implement an item-based recommendation system with Pearson similarity.

4.2.2. Model-based recommendation system

You need to use XGBregressor(a regressor based on the decision tree) to train a model. You need to use this API https://xgboost.readthedocs.io/en/latest/python/python_api.html, the XGBRegressor inside the package xgboost.

Please choose your own features from the provided extra datasets and you can think about it with customer thinking. For example, the average stars rated by a user and the number of reviews most likely influence the prediction result. You need to select other features and train a model based on that. Use the validation dataset to validate your result and remember don’t include it into your training data.

4.2.3. Hybrid recommendation system.

Now that you have the results from previous models, you will need to choose a way from the slides to combine them together and design a better hybrid recommendation system.

Here are two examples of hybrid systems:

Example1:

You can combine them together as a weighted average, which means:

𝑓𝑖𝑛𝑎𝑙 𝑠𝑐𝑜𝑟𝑒 = 𝛼 × 𝑠𝑐𝑜𝑟𝑒!”#$_&amp;’(#) + (1 − 𝛼) × 𝑠𝑐𝑜𝑟𝑒$+)#,_&amp;’(#)

Example2:

You can combine them together as a classification problem:

Again, the key idea is: the CF focuses on the neighbors of the item and the model-based RS focuses on the user and items themselves. As a result, in our dataset, some item-user pairs are more suitable for the CF while the others are not. You need to choose some features to classify which model you should choose for each item-user pair.

If you train a classifier, you are allowed to upload the pre-trained classifier model named “model.md” to save running time on Vocareum. You can use pickle library, joblib library or others if you want. Here is an example: https://scikit-learn.org/stable/modules/model_persistence.html.

You also need to upload the training script named “train.py” to let us verify your model.

-Average stars of a user, average stars of business, the variance of history review of a user or a business. -Number of reviews of a user or a business.

-The number of people think a users’ review is useful/funny/cool. Number of compliments (Be careful with these features. For example, sometimes when I visit a horrible restaurant, I will give full stars because I hope I am not the only one who wasted money and time here. Sometimes people are satirical. :-))

Input format: (we will use the following commands to execute your code) Case1:

spark-submit task2_1.py &lt;train_file_name&gt; &lt;test_file_name&gt; &lt;output_file_name&gt;

Param: train_file_name: the name of the training file (e.g., yelp_train.csv), including the file path

Param: test_file_name: the name of the testing file (e.g., yelp_val.csv), including the file path Param: output_file_name: the name of the prediction result file, including the file path Case2: spark-submit task2_2.py &lt;folder_path&gt; &lt;test_file_name&gt; &lt;output_file_name&gt;

Param: folder_path: the path of dataset folder, which contains exactly the same file as the google drive.

Param: test_file_name: the name of the testing file (e.g., yelp_val.csv), including the file path Param: output_file_name: the name of the prediction result file, including the file path Case3:

spark-submit task2_3.py &lt;folder_path&gt; &lt;test_file_name&gt; &lt;output_file_name&gt;

Param: folder_path: the path of dataset folder, which contains exactly the same file as the google drive.

Param: test_file_name: the name of the testing file (e.g., yelp_val.csv), including the file path

Param: output_file_name: the name of the prediction result file, including the file path

Output format:

a. The output file is a CSV file, containing all the prediction results for each user and business pair in the validation/testing data. The header is “user_id, business_id, prediction”. There is no requirement for the order in this task. There is no requirement for the number of decimals for the similarity values. Please refer to the format in Figure 3.

Figure 3: Output example in CSV for task2

Grading:

We will compare your prediction results against the ground truth. We will grade on all the cases in Task2 based on your accuracy using RMSE. For your reference, the table below shows the RMSE baselines and running time for predicting the validation data. The time limit of case3 is set to 30 minutes because we hope you consider this factor and try to improve on it as much as possible (hint: this will help you a lot in the competition project at the end of the semester).

Case 1 Case 2 Case 3

RMSE 1.09 1.00 0.99

Running Time 130s 400s 1800s

For grading, we will use the testing data to evaluate your recommendation systems. If you can pass the RMSE baselines in the above table, you should be able to pass the RMSE baselines for the testing data. However, if your recommendation system only passes the RMSE baselines for the validation data, you will receive 50% of the points for each case.

5. Submission

You need to submit following files on Vocareum with exactly the same name:

a. Four Python scripts:

● task1.py

● task2_1.py

● task2_2.py

● task2_3.py

b. [OPTIONAL] hw3.jar and Four Scala scripts:

● task1.scala

● task2_1.scala

● task2_2.scala

● task2_3.scala

6. Grading Criteria

(% penalty = % penalty of possible points you get)

1. You can use your free 5-day extension separately or together. (Google Forms Link for Extension: https://docs.google.com/forms/d/e/1FAIpQLSeSHzGWzPi3iuS-zNYyDLbhhP4ancMEZgKDiwYZLmhyYhKFw/viewform )

2. There will be a 10% bonus if you use both Scala and Python.

4. All submissions will be graded on Vocareum. Please strictly follow the format provided, otherwise you won’t receive points even though the answer is correct.

5. If the outputs of your program are unsorted or partially sorted, there will be 50% penalty.

6. Do NOT you use Spark DataFrame, DataSet, sparksql.

7. We can regrade your assignments within seven days once the scores are released. We will not accept any regrading requests after a week. There will be a 20% penalty if our grading is correct.

9. Only if your results from Python are correct will the bonus of using Scala be calculated. There is no partial points awarded for Scala. See the example below:

Example situations

Task Score for Python Score for Scala

(10% of previous column if correct) Total

Task 1 Correct: 3 points Correct: 3 * 10% 3.3

Task 1 Wrong: 0 point Correct: 0 * 10% 0.0

Task 1 Partially correct: 1.5 points Correct: 1.5 * 10% 1.65

Task 1 Partially correct: 1.5 points Wrong: 0 1.5

7. Common problems causing fail submission on Vocareum/FAQ

(If your program runs seem successfully on your local machine but fail on Vocareum, please check these) 1. Try your program on Vocareum terminal. Remember to set python version as python3.6,

And use the latest Spark

/opt/spark/spark-3.1.2-bin-hadoop3.2/bin/spark-submit

2. Check the input command line format.

3. Check the output format, for example, the header, tag, typos.

4. Check the requirements of sorting the results.

5. Your program scripts should be named as task1.py task2.py etc.

6. Check whether your local environment fits the assignment description, i.e. version, configuration.

8. You are required to only use Spark RDD in order to understand Spark operations more deeply. You will not get any points if you use Spark DataFrame or DataSet. Don’t import sparksql.
