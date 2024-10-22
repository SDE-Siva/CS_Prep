# Sliding Window & Two Pointer :

### 1. [Maximum Points You Can Obtain from Cards](https://leetcode.com/problems/maximum-points-you-can-obtain-from-cards/description/)

There are several cards arranged in a row, and each card has an associated number of points. The points are given in the integer array cardPoints.

In one step, you can take one card from the beginning or from the end of the row. You have to take exactly k cards.

Your score is the sum of the points of the cards you have taken.

Given the integer array cardPoints and the integer k, return the maximum score you can obtain

```java
class Solution {
    // TC : O(k + k)
    // SC : O(1)
    public int maxScore(int[] cardPoints, int k) {
        int ls = 0;
        int rs = 0;
        int maxSum = 0;
        int n = cardPoints.length;

        for(int i=0; i < k; i++){
            ls = ls + cardPoints[i];
        }
        maxSum = ls;
        int rIndex = n-1;

        for(int i = k-1; i>=0; i--){
            ls = ls - cardPoints[i];
            rs = rs + cardPoints[rIndex];
            rIndex--;

            maxSum = Math.max(maxSum, ls+rs);
        }

        return maxSum;

    }
}
```

### 2. [Max Consecutive Ones III](https://leetcode.com/problems/max-consecutive-ones-iii/description/)

Given a binary array nums and an integer k, return the maximum number of consecutive 1's in the array if you can flip at most k 0's.

```java
class Solution {
    // TC : O(2n)
    // SC : O(1)
    public int longestOnes(int[] nums, int k) {
        int ls =0;
        int rs = 0;
        int len = 0;
        int zero = 0;
        int maxLen = 0;
        int n = nums.length;

        while(rs < n){
            if(nums[rs] == 0){
                zero++;
            }

            while(zero > k){
                if(nums[ls] == 0){
                    zero--;
                }
                ls++;
            }
            len = rs - ls +1;
            maxLen = Math.max(maxLen, len);
            rs++;
        }
        return maxLen;
    }
}
```

```java
// optimized
// TC : O(n)
// SC : O(1)

class Solution {
    public int longestOnes(int[] nums, int k) {
        int ls =0;
        int rs = 0;
        int len = 0;
        int zero = 0;
        int maxLen = 0;
        int n = nums.length;

        while(rs < n){
            if(nums[rs] == 0){
                zero++;
            }

            if(zero > k){
                if(nums[ls] == 0){
                    zero--;
                }
                ls++;
            }
            if(zero <= k){
                len = rs - ls +1;
                maxLen = Math.max(maxLen, len);
            }
            rs++;
        }
        return maxLen;
    }
}
```

### 3. [Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/)

Given a string s, find the length of the longest
substring
without repeating characters

```java
class Solution {
   // TC : O(n)
   // SC : O(n) / O(256)
   public int lengthOfLongestSubstring(String s) {
       HashMap < Character, Integer > mpp = new HashMap < Character, Integer > ();

       int left = 0, right = 0;
       int n = s.length();
       int len = 0;
       while (right < n) {
           if (mpp.containsKey(s.charAt(right))){
               left = Math.max(mpp.get(s.charAt(right)) + 1, left);
           }

           mpp.put(s.charAt(right), right);

           len = Math.max(len, right - left + 1);
           right++;
       }
       return len;

   }
}
```
