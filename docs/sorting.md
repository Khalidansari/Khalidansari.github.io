# Sorting

Sorting has been of interest since the old times but one of the first algorithms were developed in 1950s. Sorting a list of elements involes reordering the elements in a particular order e.g. non-decreasing or non-increasing. We have to use words like 'non-decreasing' or 'non-increasing' instead of simply saying 'increasing' or 'decreasing' because it is better to assume that the input can have multiple elements with same value e.g. 10 13 11 20 12 13 14 13.

There are various ways developed over time to sort but they all fall in two broad categories - comparison sort and counting sort. 

For all general purpose it will be considered from now on that we want to sort the list in non-decreasing order.

## Bubble Sort

Pick the first element and compare with the second. If the first is smaller or equal to the second then do nothing else swap them. Then compare the second and third and do the same thing which we did in previous step. Then compare third and fouth. Keep on doing that till you reach the end. If you notice the elements might not be sorted still because in a way we have just ensured the largest element bubbles to the end. We will have to run the whole process again to get the second largest element just before the largest. We need to keep doing this N times to sort the elements where N is the number of elements.

E.g.

|Inital State        | New Updated State       | Logical Steps |
|--------------------|---------------------|----------|
|<span style="color:#006d51;font-weight:bold">7 8</span> 9 3 4 5 1 2 7 4 | <span style="color:#006d51;font-weight:bold">7 8</span> 9 3 4 5 1 2 7 4 | Compare first and second elements. As first is not larger than second, do nothing|
|7 <span style="color:#006d51;font-weight:bold">8 9</span> 3 4 5 1 2 7 4 | 7 <span style="color:#006d51;font-weight:bold">8 9</span> 3 4 5 1 2 7 4 | Compare second and third elements. As second is not larger than third, do nothing|
|7 8 <span style="color:#006d51;font-weight:bold">9 3</span> 4 5 1 2 7 4 | 7 8 <span style="color:#006d51;font-weight:bold">3 9</span> 4 5 1 2 7 4 | Compare third and fourth elements. As third is larger than fourth swap them|
|7 8 3 <span style="color:#006d51;font-weight:bold">9 4</span> 5 1 2 7 4 | 7 8 3 <span style="color:#006d51;font-weight:bold">4 9</span> 5 1 2 7 4 | Compare fourth and fifth elements. As fourth is larger than fifth swap them|
|7 8 3 4 <span style="color:#006d51;font-weight:bold">9 5</span> 1 2 7 4 | 7 8 3 4 <span style="color:#006d51;font-weight:bold">5 9</span> 1 2 7 4 | Compare fifth and sixth elements. As fifth is larger than sixth swap them|
|7 8 3 4 5 <span style="color:#006d51;font-weight:bold">9 1</span> 2 7 4 | 7 8 3 4 5 <span style="color:#006d51;font-weight:bold">1 9</span> 2 7 4 | Compare sixth and seventh elements. As sixth is larger than seventh swap them|
|7 8 3 4 5 1 <span style="color:#006d51;font-weight:bold">9 2</span> 7 4 | 7 8 3 4 5 1 <span style="color:#006d51;font-weight:bold">2 9</span> 7 4 | Compare seventh and eigth elements. As seventh is larger than eigth swap them|
|7 8 3 4 5 1 2 <span style="color:#006d51;font-weight:bold">9 7</span> 4 | 7 8 3 4 5 1 2 <span style="color:#006d51;font-weight:bold">7 9</span> 4 | Compare eigth and ninth elements. As eigth is larger than ninth swap them|
|7 8 3 4 5 1 2 7 <span style="color:#006d51;font-weight:bold">9 4</span> | 7 8 3 4 5 1 2 7 <span style="color:#006d51;font-weight:bold">4 9</span>| Compare ninth and tenth elements. As ninth is larger than eigth swap them|

The above is one pass over the list. If you notice, it bubbled (9), which was the largest element in the list, to the end of the list. Similarily, the second pass will bubble the second largest element (8) just before (9) and the third pass will bubble (7) just before the element (8). As said earlier, in worst case, we need to perform the above steps a total of N time where N is the number of elements. If a pass does not change the list, it means the list is sorted now and we can stop.

### Space Complexity

As it processes the list in place (It does not take the elements and put them in a separate list to process) the space used is N + 1. N is to store N elements and 1 for swapping (to hold an element temporarily).

### Time Complexity

In the worst case the list will be in decreasing order. So we will be doing N comparison in one pass and we have to make N passes in total. Which equals  $$N\times N = N^2$$. Hence worst case order is $$N^2$$. You might be thinking but I don't have to do N comparisons for all passes. For example just before the last pass, everything in the list is sorted except the first two elements. So running the last pass will take only one comparison. So let us try to find the exact number of steps to sort a list in worst case:

Pass 1 = N - 1 steps

Pass 2 = N - 2 steps

.

.

.

Pass N - 1 = 1 step

Total Steps = Sum of integers from 1 to (N - 1) = $$ \frac{(N - 1) \times (N)}{2} = \frac{N^2}{2} + \frac{N}{2}$$ = $$O(N^2)$$

What the hell is this last step? Basically what it means is that when N is really large (imagine millions), the total is not much contributed by $$\frac{N}{2}$$ as compared to what is contributed by $$\frac{N^2}{2}$$. Hey wait! We even removed the 2 from the denominator. What happened there? That is because we are interested in the order and not the exact amount. Okay, consider this. Lets say a computer program used to take 0.1 second to complete. You made some changes to the program which resulted in slowing down the execution time. What will worry you more - Time taken by a computer program to complete execution increases by a factor of 2 = 0.2? Or, when it changes by a factors 100 = 10 seconds. When we try to analyze alogirthms at a very coarse level, which generally is the case, we do what we did in that live above. It is called as big order notation. In our case of bubble sort, we will say that the worst case = $$O(N^2)$$

Big O = For large enough N the big O function should approach original O function

Small O = Same as above. Additionally the following should be true for all values of N
f(x) 

Binary Tree = each node can have two children, one child or none.

K-Ary Tree = Generalization on binary tree. They can have any number of children.

B Tree = a K-Ary Tree which is sorted at all times

While can be used when the jump is not linear - hopping different lengths or moving back and forward.

Insertion sort = How you sort cards. Insertion sort looks very similar to bubble but is better than it because it can stop current as soon as it finds the correct location of an element while in bubble sort it has to go till the end of the list anyways.

Selection sort - get the minimum from remaining list and putting it at the right place in the sorted list. Performance same as bubble sort.

counting sort = when range of values is close to the number of values. Assume the value as the index of the list

radix sort - sort the list one by one on each digit of the number - Ones place then twos place and so on

bucket sort - when the range is a lot more than what can be accomodated by counting sort but still it is possible to group numbers so that each group can be applied counting sort. E.g. 10 - 20 put in bucket 1 and apply counting sort. Put 20-30 in another bucket and sort them using counting sort. Finally merge all buckets.

merge sort - assume each element a already merged list and then merge by pairs to finally produce a single list

library sort - in insertion sort you insert an element and move all the right side elements to one place on the right. To avoid this it is better to leave space in between elements so that the right hand side elements are not required to be moved.



