# Heuristics

## Search For A Pattern

### 1.1.6

Beginning with 2 and 7, the sequence 2,7,1,4,7,4,2,8, ... is constructed by multiplying successive pairs of its members and adjoining the result as the next one or two members of the sequence, depending on whether the product is a one- or a two-digit number.  Prove that the digit 6 appears an infinite number of times in the sequence.

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

# ChatGPT's Answer

## ChatGPT
To prove that the digit 6 appears an infinite number of times in the sequence 
a<sub>1</sub>, a<sub>2</sub>, a<sub>3</sub>,... starting with a<sub>1</sub> = 2 and a<sub>2</sub> = 7, where each subsequent term is constructed by multiplying successive pairs of its members, we need to show that there are infinitely many occurrences of the digit 6 in the sequence. Here’s a step-by-step proof:

### Initial Terms and Formation Rule:

a<sub>1</sub> = 2, a<sub>2</sub> = 7
The rule states that if 
** If a<sub>i</sub> * a<sub>i+1</sub> is a one-digit nubmer, the next term is this product.
** If a<sub>i</sub> * a<sub>i+1</sub> is a two-digit nubmer, the next two terms are the digits of this product.

### Starting the Sequence

a<sub>i</sub> * a<sub>i</sub> = 2 * 7 = 14 (next two terms are 1 and 4 )
Therefore the sequence continues as:
2,7,1,4, ...

### Subsequent Terms

Continuting the rule

* a<sub>3</sub> * a<sub>4</sub> = 1 * 4 = 4 (next term is 4)
* a<sub>4</sub> * a<sub>5</sub> = 4 * 4 = 16 (next two terms are 1 and 6)

Now the sequence includes

2,7,1,4,4,1,6, ...

We can see that the digit 6 has appeared.

### Observation and Pattern:
We need to establish a pattern or show that 6 will keep appearing.
* Consider pairs of terms in which at least one of the terms is 4.
* Multiplying 4 by another number can produce numbers that includes the digit 6. For example:
  ** 4 * 4 = 16 --> 1, 6
  ** 4 * 7 = 28 --> 2, 8
  ** 4 * 1 = 4

### General Argument
Observe that once 4 appears in the sequence, we can multiply it with subsequent terms to keep generating terms that include the digit 6:

* An subsequent pair involving 4 could lead to:
  ** 4 x 4 = 16, 4 x 7 = 28, and other products like 4 x 5 = 20 (though 6 is not there)
However, within a few steps, a product involving 4 will include the digit 6 again.
Recurrence of 4:

Every time 4 appears, there are multiple future terms that involve multiplying by 4 again, leading back to numbers like 16, 24, 36, etc.
Given this continuous recurrence, we conclude that:

The digit 6 appears infinitely many times in the sequence.
The digit 6 appears infinitely many times in the sequence.
Thus, we have demonstrated that no matter how the sequence progresses, the inherent multiplication of terms involving 4 ensures that the digit 6 will keep reappearing infinitely often. This completes the proof.

## Comments on ChatGPT

ChatGPT mistakes the pattern and multiplies "the last two digits" vs keeping a counter of where we are in the multiplication.  Thus it says "2,7,1,4, *4*" vs 2,7,1,4, *7*" 

# Google's Gemini

We can prove that the digit 6 appears infinitely many times in the sequence by demonstrating that the sequence always reaches a point where it includes the numbers 2 and 4 next to each other. Once this happens, we can guarantee the repeated appearance of 6.

Here's why:

* Base Case: If at any point in the sequence we have 2 followed by any digit except 5, the next number will be a multiple of 2 ending in either 0, 2, 4, 6, or 8 (because 2 x any even number ends in 0, and 2 x any odd number except 5 ends in a multiple of 2). This means the sequence will eventually reach a combination where 2 is followed by either 0, 2, 4, or 8.
* Reaching 2 followed by 4:
  * If 2 is followed by 0, the next number will be 0, which restarts the sequence from 2 and 7. We know from the base case that this path eventually leads to 2 followed by a digit other than 5.
  * If 2 is followed by 2, 6, or 8, the next number will still be a multiple of 2. We can repeat the process from the base case until we reach 2 followed by a digit other than 0, 2, 5, 6, or 8.

The only remaining possibility is 2 followed by 4.

* Guaranteed Appearance of 6: Once we have 2 followed by 4, their product (8) will be appended to the sequence. Now, consider the next two numbers: 4 and 8. Their product (32) will result in two digits appended - 3 and 2. This creates the combination 2 followed by 3, guaranteeing the next number to be a multiple of 6 (since 2 x 3 = 6).

Therefore, from any point in the sequence, we can reach a combination of 2 followed by 4, which in turn guarantees the repeated appearance of the digit 6. This proves that 6 appears infinitely many times in the sequence.

## Comments on Gemini

Sequence using 2
2 x 2 = 4
2 x 3 = 6
2 x 4 = 8
2 x 5 = 1,0
2 x 6 = 1,2
2 x 7 = 1,4
2 x 8 = 1,6
2 x 9 = 1,8

Note that 2 isn't "followed" by 0,2,4, or 8

# New Proof

As soon as I have three 6s together (step 14) that will create
* 3,6,3,6 at the end of the string

That goes onto create three "18s" at the end of the string
* 1,8,1,8,1,8

Which then creates five "8s" at the end of the string
* 8,8,8,8,8

Which then creates four "64s" at the end of the string
* 6,4,6,4,6,4,6,4

Which then creates seven "2,4" pairs --> which creates seven "8s" of which we only need five "8s" as mentioned above.  We have infinite looping at the end of the string.

# Additional Simplification

From step 5 I have "2,8,2,8" as the end sequence.
* That will lead me to a new sequence - 1,6,1,6,1,6 (step 9)
* And that will lead to a new sequence - 6,6,6 (step 14)
* Leads to 3,6,3,6 and we use prior proof
