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
* [2.3 Failure Rate and Reliability](#failure-rate-and-reliability)
* [2.4 Decision Making Given a Target Failure Rate](#decision-making-given-a-target-failure-rate)
* [2.5 Advantages and Disadvantages of Reliability Growth Analysis](#advantages-and-disadvantages-of-reliability-growth-analysis)

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

Using the C-SFRAT tool, the group analyzed 

## Result of Range Analysis

## Failure Rate and Reliability

## Decision Making Given a Target Failure Rate

## Advantages and Disadvantages of Reliability Growth Analysis

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



<hr>

# Other

<hr>

# How The Team Work was Divided and Managed

<hr>

# Difficulties Encountered, Challenges Overcome, and Lessons Learned

<hr>

# Comments/Feedback on The Lab Itself
