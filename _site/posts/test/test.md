---
title: Day 1
date: 2024-04-09T00:00:00.000Z
author:
  - name: Omar Hayat
keywords:
  - Leetcode
  - SQL
  - Probability
jupyter: python3
execute:
  enabled: true
format: hugo-md
highlight-style: github
---


# Outline

-   **LC 5 Longest Palindromic Substring**

-   **LC 185 Department Top Three Salaries**

-   **Brain stellar: Rolling the Bullet**

## LC 5 Longest Palindromic Substring

Given a string `s`, return the longest palindromic substring in `s`.

``` python
    def longestPalindrome(self,s)->str:
        n = len(s)
        dp = [[False]*n for _ in range(n)]
        ans = [0,0]
    
        for i in range(n):
            dp[i][i] = True
    
        for i in range(n-1):
            if s[i]==s[i+1]:
                dp[i][i+1]=True
                ans = [i,i+1]
    
        for diff in range(2,n):
            for i in range(n-diff):
                j = i + diff
                if s[i] == s[j] and dp[i+1][j-1]:
                    dp[i][j] = True
                    ans = [i,j]
    
        i,j = ans
        return s[i:j+1]
```

## LC 185 Department Top Three Salaries
