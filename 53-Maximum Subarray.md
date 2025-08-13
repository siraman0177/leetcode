class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        x=y=nums[0]
        for i in range (1,len(nums)):
            x=max(nums[i],nums[i]+x)
            y=max(x,y)

        return y

        
# by using kadane's algorithm in c++

class Solution {
public:
    int maxSubArray(vector<int>& nums) {
       int currentsum=0 , maxs=INT_MIN;

       for (int i:nums){
        currentsum+=i;
        maxs=max(currentsum,maxs);

        if(currentsum<0){
            currentsum=0;
        }
       }
    return maxs;
    }
};

# kadane's algorithm states that if the sum of elements gives you a -ve no. stop consideriing them and reinitialise the current sum .
