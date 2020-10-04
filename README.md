# Find-Pivot-Index
The sum of right side of pivot element should be equal to sum of left side of pivot. 
class Solution {
    public int pivotIndex(int[] nums) {
        int totalArraySum=0;
        if(nums.length < 3){
            return -1;
        }
        for(int i=0;i<nums.length;i++){
            totalArraySum += nums[i];
        }
        int rightSum=0;
        for(int i=0;i<nums.length;i++){
        if(i-1 >= 0){
            rightSum += nums[i-1];
        }
        
        int leftSum = totalArraySum - (nums[i] + rightSum);
        if(rightSum == leftSum){
            return i;
        }
        }
        return -1;
    }
}
