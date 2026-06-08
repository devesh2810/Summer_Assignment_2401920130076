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