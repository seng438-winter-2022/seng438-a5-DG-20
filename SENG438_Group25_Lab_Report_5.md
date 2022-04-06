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

[2 Reliability Growth Testing](#reliability-growth-testing)
* [2.1 Selected Models](#selected-models)
* [2.2 Result of Range Analysis](#result-of-range-analysis)
* [2.3 Results](#esults)
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

Upon looking at the overall shape of the Results, the group determined that the best model, and the one that was chosen as a result, was Geometric (GM). Furthermore, upon looking at the Model Comparison tab, the Critic (mean) for the GM model is 1.000 which essentially presents an idea fit for the input data. The Model Comparison table is provided below for reference:
![image](https://user-images.githubusercontent.com/58268240/161902304-c5114dd8-a7ae-4bfd-86a1-180aba12b327.png)

## Result of Range Analysis

In the C-SFRAT tool, there was no option to conduct a range analysis such as Laplace. Furthermore, the CASRE tool did not work on any group member's laptop after several attempts even after data manipulation and changing the data to fit the format of the sample inputs provided.
As such, the group set the Number of Intervals to Predict as 62, to observe the expected behaviour, and whether or not the number of failures is expected to platea (steady out). This number was determined through trial and error, and the result produced is as follows:
![image](https://user-images.githubusercontent.com/58268240/161906119-5274b85b-d9c0-4396-9d3e-4caab49fef2d.png)
As can be seen, the graph is slowly but surely steading out at around 120.

## Results

## Advantages and Disadvantages of Reliability Growth Analysis

### Advantages:
* Reliability Growth Analysis is a statistical method to estimate time and costs associated with product development and the reliability goal. The reliability goal can be in the form of a Mean Time Between Failure, Annualized Failure rate, or any number of different metrics.
* Reliability Growth Analysis helps to regulate a management strategy to reach the reliability goal.
* It can be applied from early development stages until the end of life of a product. There are also various different models that are available to be utilized with Reliability Growth Analysis.

### Disadvantages:
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

<hr>

# How The Team Work was Divided and Managed

The assignment was done as a group of four as difficulties were run into for Mac users. We did this by having one group member share their screen as the other three members watched the screen and assisted in the process. This method was performed for parts one and two of the lab. In part one, one group member shared their screen as the others guided the person through the steps of part one familiarization and the instructions for running C-SFRAT. It was a learning process as nobody had worked with the application before so some learning was required. In part two, the same process was performed using RDC. All members made themselves familiar with RDC and how to use it while one member shared their screen of performing the instructions given in the lab. Members not sharing their screen took turns performing different instructions with the person sharing their screen to ensure the process was done correctly. Everybody worked together on the documenting of the lab.

<hr>

# Difficulties Encountered, Challenges Overcome, and Lessons Learned

Some difficulties encountered were getting the lab working at all. The failure set used for the importing of data was told to be in the wrong format by the application being used. In some group members cases the applications would not work at all or the failure set data would not be allowed to be imported. The lab document provided no clarification to this nor did any instruction from TA’s. The lab was extremely frustrating and many groups were confused and had no clue on how to fix any of the problems. The lab overall, was very confusing, complicated, and not functional at times. Challenges that were overcome took hours to resolve. Lessons learned was that the introduction to reliability testing taught members different aspects of reliability testing including RDC and Reliability Growth Analysis.

<hr>

# Comments/Feedback on The Lab Itself

The lab didn’t function properly for some group members as stated in the aforementioned. Some clearer instructions and or a demo on how to use the application would benefit students in the completion of the lab in the future. Overall, some applications used in reliability testing and the practices of reliability testing were learned by the students.

