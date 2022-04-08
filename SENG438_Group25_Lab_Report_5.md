**SENG 438- Software Testing, Reliability, and Quality**

**Lab. Report \#5 – Software Reliability Assessment**

| Group \#:      | 25  |
| -------------- | --- |
| Curtis Silva   |     |
| Divyansh Goyal |     |
| Gurpartap Sohi |     |
| Liam Parmar    |     |

<hr>

**Table of Contents**

[1 Introduction](#introduction)

This purpose of this lab was to introduce assessing failure data using Reliability Growth Testing and conducting a Reliability Assessment. The first part of the lab explored the use of the STRAT tool to import failure data and create plots of failure rate and reliability. The second part of the lab explored the use of a Reliability Demonstration Chart (RDC) to determine the trend for the reliability of the system.

[2 Reliability Growth Testing](#reliability-growth-testing)
* [2.1 Selected Models](#selected-models)
* [2.2 Result of Range Analysis](#result-of-range-analysis)
* [2.3 Results](#results)
* [2.4 Advantages and Disadvantages of Reliability Growth Analysis](#advantages-and-disadvantages-of-reliability-growth-analysis)

[3 RDC Testing](#rdc-testing)
* [3.1 MTTFmin Plots](#mttfmin-plots)
* [3.2 Evaluation and Justification of MTTFmin](#evaluation-and-justification-of-mttfmin)
* [3.3 Advantages and Disadvantages of RDC](#advantages-and-disadvantages-of-rdc)

[4 Other](#other)
* [4.1 Comparison of The Results](#comparison-of-the-results)
* [4.2 Similarities and Differences](#similarities-and-differences)

[5 How The Team Work was Divided and Managed](#how-the-team-work-was-divided-and-managed)

[6 Difficulties Encountered, Challenges Overcome, and Lessons Learned](#difficulties-encountered-challenges-overcome-and-lessons-learned)

[7 Comments/Feedback on The Lab Itself](#commentsfeedback-on-the-lab-itself)

<hr>

# Introduction

<hr>

# Reliability Growth Testing

## Selected Models

Using the C-SFRAT tool, the group analyzed all the available models on the failure data provided. After looking at Model Results and Predictions, the group analyzed the Results to determine the model which provided the best fit. All Models' Results are overlayed in the following image:
![image](https://user-images.githubusercontent.com/58268240/161900785-c01a237a-3f6b-4860-89bc-2cb0344a7f1d.png)
The Intensity Graph with the models overlayed are represented here:
![image](https://user-images.githubusercontent.com/58268240/161904591-331376bf-dded-4b16-98bb-0b77423abf73.png)

Upon looking at the overall shape of the Results, the group determined that the best two models, and the ones that were chosen as a result, were Geometric (GM) and S Distribution (S). Furthermore, upon looking at the Model Comparison tab, the Critic (mean) for the GM model is 1.000 which essentially presents an idea fit for the input data, and the Critic (mean) for the S model is 0.999, which is close to ideal. The Model Comparison table is provided below for reference:
![image](https://user-images.githubusercontent.com/58268240/161902304-c5114dd8-a7ae-4bfd-86a1-180aba12b327.png)

## Result of Range Analysis

In the C-SFRAT tool, there was no option to conduct a range analysis such as Laplace. Furthermore, the CASRE tool did not work on any group member's laptop after several attempts even after data manipulation and changing the data to fit the format of the sample inputs provided.
As such, the group set the Subset Failure Data Range to 18 intervals. This was done by looking at the graph and determining that the data before 19 intervals showed a steady increase whereas afterwards, it became much steeper increases. As such, the first steady rise subset was selected as the Range. The chosen models' Results are displayed below:
![image](https://user-images.githubusercontent.com/58268240/161911560-6ee1e8f6-bfa5-43fa-b4c2-a0027ea24e39.png)
As can be seen, this graph shows the Results being very close together.

To observe the expected behaviour, and whether or not the number of failures is expected to plateau (steady out) using the two models and the specified Range, the predicted value for the number of intervals was set to 36. This number was determined through trial and error, and the result produced is as follows:
![image](https://user-images.githubusercontent.com/58268240/161911880-488a31bc-9db4-4325-904d-31805101dc4f.png)
As can be seen, the graphs are slowly but surely steading out at around 52.

## Results

As the course notes state, the MTTF (target failure rate) is measured in failures per time interval. As such, using the imported data, the formula for MTTF (target failure rate) = (failures at interval 18 - failures at interval 1)/(interval 18 - interval 1) = (43 - 2)/(18 - 1) = 2.41.

## Advantages and Disadvantages of Reliability Growth Analysis

### Advantages:
* Reliability Growth Analysis is a statistical method to estimate time and costs associated with product development and the reliability goal. The reliability goal can be in the form of a Mean Time Between Failure, Annualized Failure rate, or any number of different metrics.
* Reliability Growth Analysis helps to regulate a management strategy to reach the reliability goal.
* It can be applied from early development stages until the end of life of a product. There are also various different models that are available to be utilized with Reliability Growth Analysis.
* Reliability growth analysis is conducted in a dynamic environment where the reliability can change due to corrective actions.

### Disadvantages:
* Reliability growth models may not be able to be applied to software with a lack of software failure data.
* Reliability growth models selected may have a bias or not be the best fit for a project's data, as it is determined by human choice.
<hr>

# RDC Testing

## MTTFmin Plots

### MTTFmin: 1950

![image](https://user-images.githubusercontent.com/58268240/161478621-ebc5664b-dc9a-49f4-88bb-4ad96427905b.png)

### Explanation

Here, the last observed failure is seen in the Accept (green) region. As such, it can be concluded that the SUT testing is acceptable for reliability. This value is also near the right edge (the maximum number of normalized events - 100), thus providing a suitable MTTFmin.

### Double MTTFmin: 3900

![image](https://user-images.githubusercontent.com/58268240/161477544-b061758f-5812-456b-a328-c0b5d9f8664a.png)

### Explanation

With this MTTF, it can be observed that the Observed Failures graph is almost entirely contained in the Reject region. This indicates that the test with this MTTF fails, as such indicating that 3900 is not an acceptable MTTFmin.

### Half MTTFmin: 975

![image](https://user-images.githubusercontent.com/58268240/161478353-f3cde086-dd0c-41e6-8107-94b31896e99a.png)

### Explanation

With this MTTF, it can be observed that the Observed Failures graph extends beyond the maximum number of normalized events (100) and thus extends past the Accept region. As such, 975 is not an acceptable MTTFmin because the Observed Failures graph must be contained within the three regions to make the test valid.

## Evaluation and Justification of MTTFmin

Through the documentation and the notes in the lecture slides regarding RDC, it was apparent that the MTTF is inversely proportional to the Failure Intensity (FIO) in the Failure Data sheet. After extrapolating the Failure Data to 100 normalized input events, the group followed the instructions in the lab document and utilized trial and error to change the MTTF and observe the changes in the R-Demo-Chart. Through research and the lecture notes, it was determined that an acceptable SUT test is when the Observed Failure graph line contains its final point in the Acceptable (green) region. Following this, when the group initially set the MTTF to 2500, the end point observed was in the Continue Test (yellow) region. So, the group lowered the MTTF to 1900, which then introduced a gray region in the graph as the Observed Failures surpassed 100 events, which should not happen according to the test data we passed in. Continuing trial and error, the group in conclusion determined that the best MTTF (MTTFmin) was 1950.

## Advantages and Disadvantages of RDC

### Advantages:

* Reliability Demonstration Chart analysis is a very time and cost efficient way of analyzing the reliability of a system.
* Can be used as a demonstration of reliability on a system.
* Supports decisions to be made on the system through visual reliability demonstration.

### Disadvantages:

* Cannot come up with quantitative numbers for the reliability or availability of the system under study.
* Can only demonstrate the trend of changes and how they affect systems reliability.
* Experimenting with different values of confidence levels and MTTF is tedious.

<hr>

# Other
### Comparing the results of Part 1 and Part 2

When looking at the results from part 1, an MTTF of 2.41 is extrapolated from the slope of the graph taken from interval 18 to interval 1. As can be seen in the graph, the start of interval 0 has a high amount of failures, which is expected with the most failures being the end of the final interval. The slope provides a rough estimate to ensure the failure data imported is accepted. When looking at the results from part 2, the minimum MTTF found to be best suited was 1950 through some trial and error of adjusting the RDC.
### Discussion on similarities and differences of the two techniques.

Reliability Demonstration Chart can be utilized when the failure data is limited to a few failures, and the trend for the reliability of the system is needed. It is based on inter failure time only and target failure rate. Whereas Reliability Growth Testing, is based on inter failure time and/or failure count and target failure rate.

Both Reliability Growth Testing and Reliability Demonstration Chart techniques are based on collecting failure data at time points, and requires inputting the failure data which consists of the failure number and failure time. However, in Reliability Growth Testing, a set of models are selected that would provide the best fit for the project data and a range is chosen to utilize the useful data. The range can be manipulated in Reliability Growth Testing to determine an acceptable range. In the Reliability Demonstration Chart (RDC), the target MTTF and anticipated confidence levels need to be identified. Then the failure points are drawn on the graph and the trend is analyzed. The MTTF and confidence levels can be set to various values and used to plot the failure data. Specifically, the minimum MTTF needs to be determined for which the system under test becomes acceptable. Therefore, it is an efficient way of checking whether the target failure rate or MTTF is met or not. RDC can only indicate whether a system under test is acceptable or not, it does not provide a quantitative value for the reliability.

<hr>

# How The Team Work was Divided and Managed

The assignment was done as a group of four as difficulties were run into for Mac users. We did this by having one group member share their screen as the other three members watched the screen and assisted in the process. This method was performed for parts one and two of the lab. In part one, one group member shared their screen as the others guided the person through the steps of part one familiarization and the instructions for running C-SFRAT. It was a learning process as nobody had worked with the application before so some learning was required. In part two, the same process was performed using RDC. All members made themselves familiar with RDC and how to use it while one member shared their screen of performing the instructions given in the lab. Members not sharing their screen took turns performing different instructions with the person sharing their screen to ensure the process was done correctly. Everybody worked together on the documenting of the lab.

<hr>

# Difficulties Encountered, Challenges Overcome, and Lessons Learned

Some difficulties encountered were getting the lab working at all. The failure set used for the importing of data was told to be in the wrong format by the application being used. In some group members cases the applications would not work at all or the failure set data would not be allowed to be imported. The lab document provided no clarification to this nor did any instruction from TA’s. The lab was extremely frustrating and many groups were confused and had no clue on how to fix any of the problems. The lab overall, was very confusing, complicated, and not functional at times. Challenges that were overcome took hours to resolve. Lessons learned was that the introduction to reliability testing taught members different aspects of reliability testing including RDC and Reliability Growth Analysis.

<hr>

# Comments/Feedback on The Lab Itself

The lab didn’t function properly for some group members as stated in the aforementioned. Some clearer instructions and or a demo on how to use the application would benefit students in the completion of the lab in the future. Overall, some applications used in reliability testing and the practices of reliability testing were learned by the students.
