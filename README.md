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


Picking the median of three elements in the dataset will up the chances of
chosing a good pivot. This is because these probabilities compound. The probability
of at least on of the elements chosen being a good pivot is $1 - (0.5 * 0.5 * 0.5) = 87.5%$.
The reason we choose the median of the three of these elements is because it gives
us the best chance of chosing the least extreme value of the three. Chosing the least
extreme of the three is critical because it will give us the highest chance of chosing
the one pivot that is good.


Disclaimer: This is not guarenteed however. It is all probabalistic, there is still a chance
that you get a bad pivot. However, using the median of three method provides a 37.5% boost in
chances of getting a good pivot.
