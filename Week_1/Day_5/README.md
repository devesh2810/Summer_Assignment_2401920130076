************ valid palindrome **************

class Solution {
public:
    bool isPalindrome(string s) {
        int left = 0, right = s.size() - 1;

        while (left < right) {
            while (left < right && !isalnum(s[left]))
                left++;
            while (left < right && !isalnum(s[right]))
                right--;

            if (tolower(s[left]) != tolower(s[right])) {
                return false;
            }
            left++;
            right--;
        }
        return true;
    }
};

************* reverse string ************

class Solution {
public:
    void reverseString(vector<char>& s) {
        int i=0,j=s.size()-1;
        while (j>=i)
        {
            swap(s[i++],s[j--]);
        }
        
    }
};

