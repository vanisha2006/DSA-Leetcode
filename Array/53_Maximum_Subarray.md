Problem: Maximum Subarray LC:Q53
Approch: Kadane's Algorithm
Time Complexity:O(n)
Space Complexity:O(1)

class Solution {
public:
    int maxSubArray(vector<int>& nums) {
        //Intializing is done cover the negative cases
        int fre=nums[0],ans=nums[0];
        for(int i=1;i<nums.size();i++){
            //If sum of subarray is negative,start we new subarray
            if(fre<0){
                fre=nums[i];
            }
            //Else add on
            else{
                fre+=nums[i];
            }
            //Upadating the sum of subarray
            ans=max(ans,fre);
        }
        return ans;
    }
};
