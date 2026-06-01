
************** 1. TWO SUM **************

class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        unordered_map <int, int > hash;
        int n=nums.size();
        int need=0;
        for (int i=0;i<n;i++)
        {   
           need=target-nums[i];
           if (hash.count(need))
           {
            return {hash[need],i};
           }
           hash[nums[i]]=i;
        }
    return {};  }
};


*************** 26. Remove Duplicates from Sorted Array **************

class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
        int k = 0;

        for (int num : nums) {
            if (k == 0 || num != nums[k - 1]) {
                nums[k++] = num;
            }
        }

        return k;
    }
};

**************** 121. Best time to buy and sell the stock *************

class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int n=prices.size();
        int minn=prices[0];
        int profit=0;
        for (int i=1;i<n;i++)

        {  
            minn=min(minn,prices[i]);
            profit= max(profit,prices[i]-minn);

        }
    return profit;}
};