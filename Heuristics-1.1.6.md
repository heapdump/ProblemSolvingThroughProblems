# Heuristics

## Search For A Pattern

### 1.1.6

_Prove that the digit 6 appears an infinite number of times_

Let's build out the sequence and look for a loop
1. __2,7__,1,4
1. 2,__7,1__,4,7
1. 2,7,__1,4__,7,4
1. 2,7,1,__4,7__,4,2,8
1. 2,7,1,4,__7,4__,2,8,2,8
1. 2,7,1,4,7,__4,2__,8,2,8,8
1. 2,7,1,4,7,4,__2,8__,2,8,8,1,6
1. 2,7,1,4,7,4,2,__8,2__,8,8,1,6,1,6
1. 2,7,1,4,7,4,2,8,__2,8__,8,1,6,1,6,1,6
1. 2,7,1,4,7,4,2,8,2,__8,8__,1,6,1,6,1,6,6,4
1. 2,7,1,4,7,4,2,8,2,8,__8,1__,6,1,6,1,6,6,4,8
1. 2,7,1,4,7,4,2,8,2,8,8,__1,6__,1,6,1,6,6,4,8,6
1. 2,7,1,4,7,4,2,8,2,8,8,1,__6,1__,6,1,6,6,4,8,6,6
1. 2,7,1,4,7,4,2,8,2,8,8,1,6,__1,6__,1,6,6,4,8,6,6,6
1. 2,7,1,4,7,4,2,8,2,8,8,1,6,1,__6,1__,6,6,4,8,6,6,6,6
1. 2,7,1,4,7,4,2,8,2,8,8,1,6,1,6,__1,6__,6,4,8,6,6,6,6,6
1. 2,7,1,4,7,4,2,8,2,8,8,1,6,1,6,1,__6,6__,4,8,6,6,6,6,6,3,6
1. 2,7,1,4,7,4,2,8,2,8,8,1,6,1,6,1,6,__6,4__,8,6,6,6,6,6,3,6,2,4
1. 2,7,1,4,7,4,2,8,2,8,8,1,6,1,6,1,6,6,__4,8__,6,6,6,6,6,3,6,2,4,3,2
1. 2,7,1,4,7,4,2,8,2,8,8,1,6,1,6,1,6,6,4,__8,6__,6,6,6,6,3,6,2,4,3,2,4,8
1. 2,7,1,4,7,4,2,8,2,8,8,1,6,1,6,1,6,6,4,8,__6,6__,6,6,6,3,6,2,4,3,2,4,8,3,6
1. 2,7,1,4,7,4,2,8,2,8,8,1,6,1,6,1,6,6,4,8,6,__6,6__,6,6,3,6,2,4,3,2,4,8,3,6,3,6
1. 2,7,1,4,7,4,2,8,2,8,8,1,6,1,6,1,6,6,4,8,6,6,__6,6__,6,3,6,2,4,3,2,4,8,3,6,3,6,3,6
1. 2,7,1,4,7,4,2,8,2,8,8,1,6,1,6,1,6,6,4,8,6,6,6,__6,6__,3,6,2,4,3,2,4,8,3,6,3,6,3,6,3,6
1. 2,7,1,4,7,4,2,8,2,8,8,1,6,1,6,1,6,6,4,8,6,6,6,6,__6,3__,6,2,4,3,2,4,8,3,6,3,6,3,6,3,6,1,8
1. 2,7,1,4,7,4,2,8,2,8,8,1,6,1,6,1,6,6,4,8,6,6,6,6,6,__3,6__,2,4,3,2,4,8,3,6,3,6,3,6,3,6,1,8,1,8
1. 2,7,1,4,7,4,2,8,2,8,8,1,6,1,6,1,6,6,4,8,6,6,6,6,6,3,__6,2__,4,3,2,4,8,3,6,3,6,3,6,3,6,1,8,1,8,1,2
1. 2,7,1,4,7,4,2,8,2,8,8,1,6,1,6,1,6,6,4,8,6,6,6,6,6,3,6,__2,4__,3,2,4,8,3,6,3,6,3,6,3,6,1,8,1,8,1,2,8
1. 2,7,1,4,7,4,2,8,2,8,8,1,6,1,6,1,6,6,4,8,6,6,6,6,6,3,6,2,__4,3__,2,4,8,3,6,3,6,3,6,3,6,1,8,1,8,1,2,8,1,2
1. 2,7,1,4,7,4,2,8,2,8,8,1,6,1,6,1,6,6,4,8,6,6,6,6,6,3,6,2,4,__3,2__,4,8,3,6,3,6,3,6,3,6,1,8,1,8,1,2,8,1,2,6

As soon as we see a 6 let's do an analysis of what gets put at the end of the string
If the number next to 6 is

After we multiply the second 7x4 we're in a state where we only have 4,2,8 to multiply.
Those can generate 8, 16, 64 expanding our set to digits 1,2,4,6,8.
However 6x6 and 4x8 can introduce a 3 into our set - but only as a pair 3,6 or 3,2
Similarly 2x8, 4x3 can introduce 1 but never next to a 3 (16, 12, 36).  
This means our odd numbers will never be next to each other and will always be multiplied by 2,4,6,8.
When that happens we will generate sequences of numbers in the same set [1,2,3,4,6,8]

Suppose we generate a 6 - we don't know what the last number will be, but it must be in our set. Let's do the cases.
* Case 1 - 1x6 = 6 - we have generated another 6.
* Case 2 - 2x6 = 1,2 = 1,2,2,4,8,3,2,2,4,6 - we have generated another 6
* Case 3 - 3x6 = 1,8 = 1,8,8,6,4 - we have generated another 6
* Case 4 - 4x6 = 2,4 = 2,4,8 - same as Case 2
* Case 5 - Not applicable, outside of set
* Case 6 - 6x6 = 3,6 = same as Case 3
* Case 7 - Not applicable, outside of set
* Case 8 - 6x8 = 4,8 = 4,8,3,2,6 - we have generated another 6
* Case 9 - Not applicable, outside of set

Thus, as soon as we generate a 6 - we know we will generate another one given all the numbers are in the set [1,2,3,4,6,8]
In this case - we satisfy the criteria on the 7th step of the sequence

