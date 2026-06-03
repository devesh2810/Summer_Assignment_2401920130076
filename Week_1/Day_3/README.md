
************ Move zeroes *************

class Solution {
public:
    void moveZeroes(vector<int>& nums) {
        int low=0;
        for (int i=0;i<nums.size();i++)
        {   
            if (nums[i]!=0)
            {
                swap(nums[low],nums[i]);
                low++;
            }
        }
    }
};

************ Squares of a sorted array ***********

class Solution {
public:
    vector<int> sortedSquares(vector<int>& nums) {
        int start=0;
        int end=nums.size()-1;
        int pos=end;
        vector <int> result(end+1);
        while (start<=end)
        {
            if ((nums[start]*nums[start])> (nums[end]*nums[end]))
            {
                result[pos]=nums[start]*nums[start];
                pos--;
                start++;
            }
            else
            {
                result[pos]=nums[end]*nums[end];
                pos--;
                end--;
            }


        }
        


        
        return result;

    }
};

*************** container with most water ***********