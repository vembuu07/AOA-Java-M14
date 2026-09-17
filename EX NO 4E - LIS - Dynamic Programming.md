
# EX 4E Longest Increasing Subsequence - Dynamic Programming.
## DATE:09/09/26
## AIM:
To write a Java program to for given constraints.
Given an integer array nums, return the length of the longest strictly increasing subsequence.
Example 1:
Input: nums = [10,9,2,5,3,7,101,18]
Output: 4
Explanation: The longest increasing subsequence is [2,3,7,101], therefore the length is 4.
## Algorithm
1.Start and read the number of elements n, then input the array nums[].

2.Initialize a DP array dp[] with all values as 1 (each element is an LIS of length 1).

3.For each element i from 1 to n-1, compare with all previous elements j < i.

4.If nums[i] > nums[j], update dp[i] = max(dp[i], dp[j] + 1).

5.After filling the DP array, the maximum value in dp[] is the length of the Longest Increasing Subsequence.
  

## Program:
```
/*
Program to implement Reverse a String
Developed by: PAVITHRA S
Register Number: 212223230147
*/
import java.util.*;

public class LongestIncreasingSubsequence {

    public static int lengthOfLIS(int[] nums) {
        
       int[] dp=new int[nums.length];
       Arrays.fill(dp,1);
       for(int i=1;i<nums.length;i++){
           for(int j=0;j<i;j++){
               if(nums[i]>nums[j]){
                   dp[i]=Math.max(dp[i],dp[j]+1);
               }
           }
       }
       int longest=0;
       for(int c:dp){
           longest=Math.max(longest,c);
       }
       return longest;
        
    }

public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Prompt user input
        int n = scanner.nextInt();
        int[] nums = new int[n];

        for (int i = 0; i < n; i++) {
            nums[i] = scanner.nextInt();
        }

        // Calculate and display the length of LIS
        int result = lengthOfLIS(nums);
        System.out.println("Length of Longest Increasing Subsequence: " + result);

        scanner.close();
    }
}

```

## Output:

<img width="815" height="249" alt="image" src="https://github.com/user-attachments/assets/66bd3506-249e-4700-b247-c4ef978cd779" />


## Result:
The program successfully implemented and the expected output is verified.
