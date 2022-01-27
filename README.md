# Find-First-and-Last-Position-of-Element-in-Sorted-Array
Find First and Last Position of Element in Sorted Array - Leetcode - Problem Solution

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
