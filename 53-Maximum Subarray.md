class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        x=y=nums[0]
        for i in range (1,len(nums)):
            x=max(nums[i],nums[i]+x)
            y=max(x,y)

        return y

        
