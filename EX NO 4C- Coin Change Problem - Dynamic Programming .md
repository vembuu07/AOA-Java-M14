
# EX 4C Coin Change Problem - Dynamic Programming.
## DATE:09/09/26
## AIM:
To write a Java program to for given constraints.
You are given an integer array coins representing coins of different denominations and an integer amount representing a total amount of money.

Return the fewest number of coins that you need to make up that amount. If that amount of money cannot be made up by any combination of the coins, return -1.

You may assume that you have an infinite number of each kind of coin.

## Algorithm
1.Start and read the list of coin denominations and the target amount.

2.Initialize a DP array dp[] of size amount + 1, where dp[i] stores the minimum number of coins to make amount i.

3.Set all values in dp[] to a large number (amount + 1) and set dp[0] = 0.

4.For each amount i from 1 to amount, check all coins:
If coin <= i, update dp[i] = min(dp[i], dp[i - coin] + 1).

5.Return dp[amount] if it’s valid; otherwise, return -1 (not possible).
  

## Program:
```
/*
Program to implement Reverse a String
Developed by: PAVITHRA S
Register Number: 212223230147
*/

import java.util.*;

public class Solution {
    public int coinChange(int[] coins, int amount) {
        //ADD YOUR CODE HERE
        int max=amount+1;
        int[] dp =new int[amount+1];
        Arrays.fill(dp,max);
        dp[0]=0;
        for(int i=1;i<=amount;i++) {
            for(int coin : coins) {
                if(coin<=i) {
                    dp[i]=Math.min(dp[i],dp[i-coin]+1);
                }
            }
        }
       return dp[amount]>amount?-1:dp[amount]; 
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Solution solution = new Solution();
        String coinsLine = scanner.nextLine(); 
        String amountLine = scanner.nextLine();
        coinsLine = coinsLine.replaceAll("[^0-9,]", ""); 
        String[] coinsStr = coinsLine.split(",");
        int[] coins = new int[coinsStr.length];
        for (int i = 0; i < coinsStr.length; i++) {
            coins[i] = Integer.parseInt(coinsStr[i]);
        }
        int amount = Integer.parseInt(amountLine.replaceAll("[^0-9]", ""));
        int result = solution.coinChange(coins, amount);
        System.out.println(result);

        scanner.close();
    }
}
```

## Output:

<img width="330" height="237" alt="image" src="https://github.com/user-attachments/assets/1f5a12a7-91cc-43c4-adef-77e96d3751ef" />


## Result:
The program successfully implemented and the expected output is verified.
