## Problem
Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

 

Example 1:

Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
Example 2:

Input: nums = [3,2,4], target = 6
Output: [1,2]
Example 3:

Input: nums = [3,3], target = 6
Output: [0,1]

> :memo: **Note:** I need to finish it, there is one case that i have to cover.

## Solution

```
class Solution {
    fun twoSum(nums: IntArray, target: Int): IntArray {
       var resultArray = intArrayOf(0,0)
        // remove elements bigger than target
       val numsModified = nums.filter { it < target }.toTypedArray()
        // ordering array 
       numsModified.sort()
       // taking the first element as reference 
       resultArray[0] = numsModified[0]
       // find elements that their sum is equals to target 
       for (i in numsModified.indices){
         if(i == 0)
             continue
         if(resultArray[0] + numsModified[i] == target){
             resultArray[1] = numsModified[i]
             break
         }
       }
        // find indices that elements
       resultArray[0] = nums.indexOf(resultArray[0])
       resultArray[1] = nums.indexOf(resultArray[1])

       return resultArray
    }
       
}
```