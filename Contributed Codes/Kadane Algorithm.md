## Kadane Algorithm

### Question: Maximum Subarray
```
Given an integer array nums, 
find the contiguous subarray (containing at least one number) which has the largest sum and return its sum.
A subarray is a contiguous part of an array.
Input: nums = [-2,1,-3,4,-1,2,1,-5,4]
Output: 6
Explanation: [4,-1,2,1] has the largest sum = 6.
Constraints :
1 <= nums.length <= 10^5
-10^4 <= nums[i] <= 10^4
```
>**Approach for "Maximum Sum Contiguous Subarray Question" using "Kadane Algorithm"** <br>
>**Time Complexity : O(N)** <br>
>**Space Complexity : O(1)** <br>
```
#include<bits/stdc++.h>
using namespace std;
int max_SubArraySum(int nums[], int size)
{
    int currentMax = INT_MIN, tempMax = 0;
 
    for (int i = 0; i < size; i++)
    {
        tempMax = tempMax + nums[i];
        if (currentMax < tempMax)
            currentMax = tempMax;
 
        if (tempMax < 0)
            tempMax = 0;
    }
    return currentMax;
}
int main() {
   int nums[] = {-2, 1, -3, 4, -1, 2, 1, -5, 4};
   int n = sizeof(nums)/sizeof(nums[0]);
   
   int max_sum = max_SubArraySum(nums, n);
   cout << "Maximum Subarray Sum is " << max_sum;
   return 0;
}
```
