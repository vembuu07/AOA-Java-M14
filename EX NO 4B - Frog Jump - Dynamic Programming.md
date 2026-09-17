
# EX 4B Frog Jump - Dynamic Programming.
## DATE:09/09/26
## AIM:
To write a Java program to for given constraints.
A Frog Jump 1 or 2 steps at a time.
Problem Statement:

A frog is at the bottom of the stairs with n steps. It can jump either 1 or 2 steps at a time. Write a program to find the number of distinct ways the frog can reach the top (n-th step).

Input Format:

A single integer n (1 ≤ n ≤ 45) – number of steps.
 Output Format:

A single integer – number of distinct ways to reach step n.

## Algorithm
1.Start and read the number of steps n.

2.If n <= 1, there is only one way to reach the top.

3.Create a DP array dp[] where dp[i] stores the number of ways to reach step i.

4.Initialize dp[0] = 1 and dp[1] = 1, then use the relation dp[i] = dp[i-1] + dp[i-2] for i ≥ 2.

5.Output dp[n], which represents the total number of ways the frog can reach the top.

## Program:
```
/*
Program to implement Reverse a String
Developed by: PAVITHRA S
Register Number: 212223230147
*/
import java.util.Scanner;

public class FrogJump {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int n = scanner.nextInt();
        scanner.close();
        System.out.println(countWays(n));
    }

    public static int countWays(int n) {
        if (n <= 1) return 1;
        int[] dp = new int[n + 1];
        dp[0] = 1;
        dp[1] = 1;
        for (int i = 2; i <= n; i++) {
            dp[i] = dp[i - 1] + dp[i - 2];
        }
        return dp[n];
    }
}

```

## Output:

<img width="321" height="182" alt="image" src="https://github.com/user-attachments/assets/ff2462bc-1737-4f29-ba66-c61d96f933b8" />


## Result:
The program successfully implemented and the expected output is verified.
