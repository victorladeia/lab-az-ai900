# lab-az-ai900
Repo for Lab in AI 900 prep certification from DIO course.

# Step-by-Step

All tasks done can be found on link below:
<br>
https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/01-machine-learning.html


## Steps

1. In Azure Machine Learning studio, view the Automated ML page (under Authoring).

2. Create a new Automated ML job with the following settings, using Next as required to progress through the user interface:

Basic settings:

Job name: mslearn-bike-automl<br>
New experiment name: mslearn-bike-rental<br>
Description: Automated machine learning for bike rental prediction<br>
Tags: none<br>
Task type & data:<br>

Select task type: Regression<br>
Select dataset: Create a new dataset with the following settings:<br>
Data type:<br>
Name: bike-rentals<br>
Description: Historic bike rental data<br>
Type: Tabular<br>
Data source:<br>
Select From web files<br>
Web URL:<br>
Web URL: https://aka.ms/bike-rentals<br>
Skip data validation: do not select<br>
Settings:<br>
File format: Delimited<br>
Delimiter: Comma<br>
Encoding: UTF-8<br>
Column headers: Only first file has headers<br>
Skip rows: None<br>
Dataset contains multi-line data: do not select<br>
Schema:<br>
Include all columns other than Path<br>
Review the automatically detected types<br>
Select Create. After the dataset is created, select the bike-rentals dataset to continue to submit the Automated ML job.<br>

Task settings:

Task type: Regression<br>
Dataset: bike-rentals<br>
Target column: Rentals (integer)<br>
Additional configuration settings:<br>
Primary metric: Normalized root mean squared error<br>
Explain best model: Unselected<br>
Use all supported models: Unselected. You’ll restrict the job to try only a few specific algorithms.<br>
Allowed models: Select only RandomForest and LightGBM — normally you’d want to try as many as possible, but each model added increases the time it takes to run the job.<br>
Limits: Expand this section<br>
Max trials: 3<br>
Max concurrent trials: 3<br>
Max nodes: 3<br>
Metric score threshold: 0.085 (so that if a model achieves a normalized root mean squared error metric score of 0.085 or less, the job ends.)<br>
Timeout: 15<br>
Iteration timeout: 15<br>
Enable early termination: Selected<br>
Validation and test:<br>
Validation type: Train-validation split<br>
Percentage of validation data: 10<br>
Test dataset: None<br>
Compute:

Select compute type: Serverless<br>
Virtual machine type: CPU<br>
Virtual machine tier: Dedicated<br>
Virtual machine size: Standard_DS3_V2*<br>
Number of instances: 1<br>
* If your subscription restricts the VM sizes available to you, choose any available size.<br>

3. Submit the training job. It starts automatically.

4. Wait for the job to finish. It might take a while — now might be a good time for a coffee break!
