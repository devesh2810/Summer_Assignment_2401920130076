******** valid anagram *********

class Solution {
public:
    bool isAnagram(string s, string t) {
        int i, count=0;
        int n=s.size();
        vector <int> hash(26,0);
        if (s.size()!=t.size())
        {
            return false;
        }
        else 
        {
            for (i=0;i<n;i++)
            {
                hash[s[i]-'a']++;
                hash[t[i]-'a']--;
            }
        }
        if (all_of(hash.begin(),hash.end(),[](int x) {return x==0;}))
        {
            return true;
        }
        else 
        {
            return false;
        }
        
    }
};

******* first unique character ina string *******

class Solution {
public:
    int firstUniqChar(string s) {
        int freq[26] = {0};

        for (char c : s) {
            freq[c - 'a']++;
        }

        for (int i = 0; i < s.size(); i++) {
            if (freq[s[i] - 'a'] == 1) {
                return i;
            }
        }

        return -1;
    }
};