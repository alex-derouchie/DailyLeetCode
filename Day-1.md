Problem #283: Move Zeroes

Given an integer array nums, move all 0's to the end of it while maintaining the relative order of the non-zero elements.

Note that you must do this in-place without making a copy of the array.

Example 1:

Input: nums = [0,1,0,3,12] Output: [1,3,12,0,0] Example 2:

Input: nums = [0] Output: [0]

Constraints:

1 <= nums.length <= 104 -231 <= nums[i] <= 231 - 1

Problem Solution:

class Solution {
    public void moveZeroes(int[] nums) {
        int nonZero = 0; 
        for(int i=0;i<nums.length;i++){
            if(nums[i] != 0){ 
                if(nonZero != i){
                    nums[nonZero] = nums[i];
                    nums[i] = 0;
                } 
                nonZero++; 
            } 
        } 
    } 
}

Notes: This solution is pretty straightforward. The method loops through the input array with a two pointer approach, keeping track of the current item in the loop and the current index to insert a non-zero value into (the earliest known zero). when a nonzero item is found, it essentially swaps the earliest known zero with the non-zero element, and repeats until the loop is complete.