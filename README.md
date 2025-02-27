# Quicksort Pivots
I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice.

in the lectures I only briefly mentioned strategies for determining a good pivot
for quicksort. The implementation on the slides simply picks the leftmost
element in the part of the array that we consider as a pivot. I also mentioned a
few other ways of picking a good pivot, e.g. randomly.

Median-of-three is also a good way of picking a pivot -- inspect the first,
middle, and last elements of the part of the array under consideration and
choose the median value. Using the probabilities for picking a pivot in a
particular part of the array (in the same way as we did on slide 34), argue
whether this method is more or less (or equally) likely to pick a good pivot
compared to simply choosing the first element. Assume that all permutations are
equally likely, i.e. the input array is ordered randomly.

Your answer must derive probabilities for choosing a good pivot and
quantitatively reason with them.

We assume the array of elements to be sorted is uniformly distributed, this is
because a uniform distribution represents the average case. 


We define a good pivot as being in the middle 50% of a set of data, excluding
the outer quartiles. To choose any random number in the array will give a 50%
chance of being a good pivot. This is due to the assumption that the array is
uniformly distributed.


We will start by showing the different cases in which a good or bad pivot would arise:

3 Good, 0 Bad (Can only happen once)

2 Good, 1 Bad (Can happen 3 times)

1 Good, 2 Bad (Can happen 3 times)

0 Good, 3 Bad (Can only happen once)


For the 3 Good, 0 Bad it will always result in a good pivot. 2 Good, 1 Bad will also always
return a good pivot because you take the median element and since there are two good elements,
taking the median one will always be a good pivot. Alternatively, the 0 Good, 3 Bad will always
return bad pivots.


As for the 1 Good, 2 Bad this has four different permutations because order matters, L-R-M will
represent the quartiles:

2-1-0  This would result in a bad pivot
1-1-1  This would result in a good pivot
1-1-1 (order matters) Also results in a good pivot
0-1-2  This would result in a bad pivot

Therefore, the 1 Good, 2 Bad would result in a 50% chance of having a good pivot.


So we have $(1/8)*1 + (3/8)*3 + (3/8)*0.5 + (1/8)*0 = 68.75$%.

This means the median of three will give an 18.75% higher chance of choosing a good pivot than
you would from picking a random pivot.



