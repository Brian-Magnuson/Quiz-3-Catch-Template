# Completing and Submitting this Assignment

## Method 1: Github Codespaces (Easiest)
Provided with this Github page is a Codespaces template that allows you to develop, compile, debug, and test this programming quiz from the cloud, either in your browser or through VSCode on your desktop. It includes a provided installation of Catch2 so that you do not need to install any additional software or libraries to start working. 

To get started, simply click "Use this template" in the top right of the GitHub window, and then select the "Create a new repository" option to make a personal (private!) copy of the template to work in. From there, click the green "Code" button, then click the "Codespaces" tab, and then "Create codespace on main". This will then generate your very own Codespace to work with which operates much the same as VSCode. 

From here, you can either work in your browser, or open your Codespace through VSCode on your desktop and use any extra themes, settings, or extensions you might have installed.

See [this link](url_tbd) for a video tutorial of the above and more detail on using the development environment in case you are unfamiliar with VSCode and CMake.

Note that you get 120 "core hours" per month by default, and 180 with a GitHub Premium account, included with the free [GitHub Student Developer Pack](https://education.github.com/pack). "Core hours" are calculated by multiplying the number of CPU cores in your virtual by the actual number of hours you use the software for. So, with the (perfectly sufficient) 2-core default, you get 60/90 hours of actual use, which should be plenty for this course. 

In the case that you do run out of hours or you simply no longer wish to use Codespaces, as long as you've been regularly committing to your GitHub repo, you can simply clone your work to your local machine and work on it the regular way, detailed below.

# Assignment Description: Interquartile Range

Quartiles are used in statistics to classify data. 
Per their name, they divide data into quarters.   

Given a set of data: [1, 2, 3, 4, 5, 6, 7] 
 
The lower quartile (Q1) would be the value that 
separates the lowest quarter of the data from
the rest of the data set. So, in this instance, 
Q1 = 2. The middle quartile (also known
as the median or Q2) separates the lowest 2 quarters
of the data from the rest of the data set. In
this case, Q2 = 4. The upper quartile (Q3) 
separates the lowest 3 quarters of the data 
from the rest of the data set. In this case, Q3 = 6.
The interquartile range (IQR) is the difference between
the third quartile and the first quartile: Q3 - Q1. 

In case the number of values in the list are *odd*,
the central element is a unique element. 
Example, if the list has *size = 9*. 
The *fifth element* in the list will be the median.
In case the number of values in the list are *even*, 
the central element is a average of two elements. 
Example, if the list has *size = 10*. 
The *average of fifth and sixth element* in the
list will be the median. Q1 is the median of 
the beginning and the element preceding median,
 and Q3 is the median of the element succeeding
  median and the end. 

Another example, if the data were [1, 2, 3, 4]
- Q2 = Average of 2 and 3 = 2.5
- Q1 = List consisting of elements: 1, 2 (everything before median) = Average of 1 and 2 = 1.5
- Q3 = List consisting of elements: 3, 4 (everything after median) = Average of 3 and 4 = 3.5
- IQR = 3.5 - 1.5 = 2.00

&nbsp;
***
&nbsp;


## Problem Statement
Given a sorted singly linked list without a tail 
(e.g, head -> 1 -> 2 -> 3 -> 4), return the 
interquartile range of the data set using 
the slow and fast pointer approach OR 
using a methodology that does not iterate 
over the linked list twice. **You must not iterate 
over the entire linked list more than once and you
cannot use arrays, vectors, lists or an STL 
implementation of List ADT in this problem.** 
If you prohibit the above requirements, you will
incur a 20% penalty on your score.   

The following Node class is already defined 
for you and we have already implemented the 
insert() and main() function:

```c++
class Node {
    public:
        int value;
        Node* next = nullptr;
};
```

### Restriction:
For this problem, we ask that you use properties of lists rather than using another container,
for example you cannot move all of the elements into a vector and then find the IQR of the vector.
Additionally, you should not count the elements of the list and use this count
to determine the locations of Q1 and Q3 in the list (e.g. count/4 and 3*count/4).
Instead, you should use the properties of linked lists and list traversal ideas we've brought up
in class/discussion to solve this problem.
(Hint: Think about how you can adapt the slow/fast pointer technique to solve this problem).

Some examples of acceptable code structures would be
using one loop with any number of conditionals outside the loop,
or using a divide and conquer approach.

Note: When using fast/slow pointer to find a median,
you may use the size of the list to see if it's even or odd,
as this determines how you will find the median.
If you are counting the nodes in the list to use it in this capacity,
it is acceptable for this problem.
**Any other use of a count for this problem is not allowed.**

### Sample Input:
```c++
2 4 4 5 6 7 8
```

### Sample Output:
```c++
3.00 
```

### Explanation:
- Input is a set of numbers inserted into a 
Linked List separated by spaces.
- The head of this linked list is passed into the 
 interQuartile() function. 
- Output is the Interquartile Range of the list, 
a floating point value. IQR = Q3-Q1 = 7-4 = 3.00. 
We are rounding returned values to two decimal 
places in main using setprecision().
- Note you are expected to return a floating point
 value. Also, there are a a variety of definitions 
 of IQR and we will use the definition listed here: https://www.calculatorsoup.com/calculators/statistics/quartile-calculator.php 
- You can use the calculator at above link to generate
 sample test cases.

### Constraints
- The list can contain any integers.
- The list will have at least 4 values.
- The list is sorted.

### Difficulty
Hard (+60 minutes)  

**Author:** `Robert Casanova and Amanpreet Kapoor`, 
**Date Created:** `13 Sep 2020`, 
**Last Modified:** `10 Sep 2022`