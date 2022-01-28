# Problem Solution: 
  Find-First-and-Last-Position-of-Element-in-Sorted-Array
  
# Difficulty: 
  Medium
  
# Description:
  Given an array of integers nums sorted in non-decreasing order, find the starting and ending position of a given target value.

  If target is not found in the array, return [-1, -1].

  You must write an algorithm with O(log n) runtime complexity.

  Example:

  Input: nums = [5,7,7,8,8,10], target = 8
  Output: [3,4]
  
  For more details: https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/
  
# Idea:
  We need four variables: left, right, first_pos,last_pos
    - left:
      + Going from the first index to the lsat index of the given array.
      + Once "array[left] = target", we assign 'left' to 'last_pos'
      + The final value of 'last_pos' is The Last Position Of Target.
      
    - right:
      + Going from the last index to the first index of the given array.
      + Once "array[right] = target", we assign 'right' to 'first_pos'
      + The final value of 'first_pos' is The First Position Of Target.
# Code:
  vector<int> searchRange(vector<int>& nums, int target) {
        int count(0);
        int len = nums.size();
        int left(0), right(len-1);
        int first_pos,last_pos;
        while(left<len){
            if(nums[left]==target){
                last_pos = left;
                count++;
            }
            if(nums[right]==target){
                first_pos = right;
                count++;
            }
            left++;
            right--;
        }
        if(count == 0)
            return {-1,-1};
        return {first_pos,last_pos};
        
    }
  
  


