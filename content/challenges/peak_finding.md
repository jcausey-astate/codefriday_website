---
title: "Challenge 3: Peak Finding"

draft: false
date:        "2014-10-03"
publishdate: "2014-10-03"

summary: |
    This challenge consists of finding all peak values in a timeseries dataset, determining some information about periodicity, 
    and predicting the timing of future peaks.<br>
    **Paradigm:** _Structured Programming or OOP_<br>
    **Difficulty Level:** _Beginner/Intermediate_
---

# Challenge 3: Peak Finding

## Background

Many sources of data that we encounter in programming produce _timeseries_ data.  That means that the data values are produced at specific points in time, often (but not always) at regular intervals.  Examples of timeseries data would include stock market prices, river levels, temperature over time, etc.

A common data-processing task related to timeseries data is to find places in the data where _peaks_ occur.  A peak can be formally defined as a local maxima whose value exceeds some threshold of significance with respect to the surrounding data.  Imagine a graph of the average temperature (measured from ice cores) for the past 800000 years:

![Temperature Graph](images/historical_temperature.jpg "Image from: http://projects.kmi.open.ac.uk/role/moodle/mod/page/view.php?id=625")

<!-- <small><i>Image from: http://projects.kmi.open.ac.uk/role/moodle/mod/page/view.php?id=625</i></small> -->

Many peaks and valleys can be clearly seen in the graph.  Data analysis algorithms are often required to locate these peaks in (sometimes noisy) data, and store those locations for use by other parts of the software.

Many algorithms exist for peak finding, depending on whether or not _all_ peaks need to be located, or just a _single_ peak.  The simplest algorithm for finding _all_ peaks is to simply consider each data point's relationship to its two neighboring points.  If the data point is "higher" than both neighbors, it represents a local maxima.  

The tricky part is deciding whether the local maxima is significant or not (especially if the data is noisy).  Often a simple thresholding approach is used: "Is the value at the local maxima greater than _**t**_?" Where _**t**_ is some pre-defined threshold value.  In the graph above, perhaps _**0**_ is chosen as the threshold.  There would be 5 peaks whose magnitude is greater than the threshold.  This still leaves a problem of multiple "noise" peaks being found if the data is not increasing and decreasing smoothly.  Look at the data around 0, 125 and 405 thousand years ago to see how this could be a problem.

## Challenge

This challenge is in two parts: 
1. Given a set of timeseries data in a text-based input file, determine where _all_ sigificant peaks occur in the data.
2. If the dataset contains peaks that are roughly periodic in nature, calculate the average period, and use that to predict future peaks.

### Specifics

#### 1. Determine Peak Locations 

A file containing information on the number of searches performed per week related to the terms "solar eclipse" and "eclipse" is provided (see attachments below).  Using this file as sample data, you should create a program capable of reading the file and locating all significant peaks within the file.  You should (at a minimum) display the dates for the weeks corresponding to the peaks in the data.  Please allow the user to enter the file name so that different data files can be used.

#### 2. Determine Period and Predict Future Peaks

The data provided happens to contain peaks that are roughly periodic (they occur in predictable cycles).  For part 2 of this challenge, you will determine if the data is roughly periodic, determine the aproximate period of peaks if it is, and also (if the data is periodic) extrapolate the locations of expected future peaks for some period of time.  For this challenge, 1 year will be a sufficient length of time for future prediction.  Also, if the data is periodic, but some expected peaks are missing, your program should report locations (weeks, in this case) where peaks would be expected, but do not occur.

## Test Data

The file <tt>*"eclipse_searches.data"*</tt> (attached below) contains lines corresponding to weeks of search data obtained from Google Trends, for a combination of the search terms "solar eclipse" and "eclipse".  

The data is formatted as follows:

    WEEK-START-DATE--WEEK-END-DATE NUMBER_OF_SEARCHES

Where the week's date range consists of two dates in the form:      
_`YYYY-MM-DD`_       
that are separated by a double-hyphen (`"--"`).  The first date is the beginning date for that week, and the second date is the end date.

The number of searches is just an integer value.  There is a single space separating the two pieces of information in the file.  Each line is terminated with a UNIX-style endline (`'\n'`), including the  last line in the file.

Ten lines from the file are shown below for reference:

    2009-06-07--2009-06-13 14
    2009-06-14--2009-06-20 14
    2009-06-21--2009-06-27 16
    2009-06-28--2009-07-04 15
    2009-07-05--2009-07-11 18
    2009-07-12--2009-07-18 22
    2009-07-19--2009-07-25 136
    2009-07-26--2009-08-01 19
    2009-08-02--2009-08-08 18
    2009-08-09--2009-08-15 16

---

### Dataset Download

* [eclipse_searches.data](/files/eclipse_searches.data)

