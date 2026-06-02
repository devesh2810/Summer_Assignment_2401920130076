************* Maximum Subarray ***************

class Solution {
public:
    int maxSubArray(vector<int>& nums) {
        int maxx = INT_MIN;
        int sum = 0;
        for (int i = 0; i < nums.size(); i++) {
            sum += nums[i];
            maxx = max(sum, maxx);
            if (sum < 0) {
                sum = 0;
            }

            
        }

        return maxx;
    }
};


************** Contains duplicate ************

class Solution {
public:
    bool containsDuplicate(vector<int>& nums) {
        unordered_set<int> seen;

        for (int num : nums) {
            if (!seen.insert(num).second) {
                return true;
            }
        }

        return false;
    }
};
