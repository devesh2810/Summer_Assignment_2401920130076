********* longest substring without repeating characters *********
class Solution {
public:
    int lengthOfLongestSubstring(string s) {
        vector<int> freq(256, 0);

        int left = 0;
        int ans = 0;

        for (int right = 0; right < s.size(); right++) {
            freq[s[right]]++;

            while (freq[s[right]] > 1) {
                freq[s[left]]--;
                left++;
            }

            ans = max(ans, right - left + 1);
        }

        return ans;
    }
};

********* permutation in a string ********

class Solution {
public:
    bool checkInclusion(string s1, string s2) {
        int n = s1.size();
        int m = s2.size();

        if (n > m) return false;

        vector<int> cnt1(26, 0);
        vector<int> cnt2(26, 0);

        for (char c : s1)
            cnt1[c - 'a']++;

        for (int i = 0; i < n; i++)
            cnt2[s2[i] - 'a']++;

        if (cnt1 == cnt2) return true;

        for (int i = n; i < m; i++) {
            cnt2[s2[i] - 'a']++;
            cnt2[s2[i - n] - 'a']--;

            if (cnt1 == cnt2)
                return true;
        }

        return false;
    }
};

********* find all anagram in a string *********

class Solution {
public:
    vector<int> findAnagrams(string s, string p) {
        vector<int> ans;

        int n = p.size();
        int m = s.size();

        if (n > m) return ans;

        vector<int> cntP(26, 0);
        vector<int> cntS(26, 0);

        for (char c : p)
            cntP[c - 'a']++;

        for (int i = 0; i < n; i++)
            cntS[s[i] - 'a']++;

        if (cntP == cntS)
            ans.push_back(0);

        for (int i = n; i < m; i++) {
            cntS[s[i] - 'a']++;
            cntS[s[i - n] - 'a']--;

            if (cntP == cntS)
                ans.push_back(i - n + 1);
        }

        return ans;
    }
};