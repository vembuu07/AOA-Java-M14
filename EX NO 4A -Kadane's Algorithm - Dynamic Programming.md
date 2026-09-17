
# EX 4A Kadane's Algorithm - Dynamic Programming. 
## DATE:09/09/26-
## AIM:
To Write a Java program to solve the below problem using Kadane's Algorithm.
A solar company installs solar panels around a circular grid of n buildings. Each building either generates or consumes net energy, represented by integers (+ve for generated, -ve for consumed).

The company wants to find a contiguous sequence of buildings (possibly wrapping around from the end to the beginning) that maximizes the total net energy.

Write a program to compute the maximum net energy that can be collected from any contiguous block of buildings on the circular grid.

Input Format:
First line: Integer n (number of buildings)

Second line: n space-separated integers: net energy for each building

Output Format:
A single integer: Maximum net energy collectable from a contiguous block (wrapping allowed)

Constraints:
1 <= n <= 10^6
## Algorithm
1.Start and read the number of solar panels and their energy values into an array.

2.Calculate the total sum of all energy values.

3.Find the maximum subarray sum (non-circular case) using Kadane’s algorithm.

4.Find the minimum subarray sum and compute the circular sum as totalSum - minSum.

5.Return the maximum of maxSum and circularSum (handle all-negative case separately).
   

## Program:
```
/*
Program to implement Reverse a String
Developed by: PAVITHRA S
Register Number: 212223230147
*/
import java.util.*;

public class SolarEnergyMaximizer {

    public static int maxCircularEnergy(int[] energy)     {
        //Type your code
        int sum=0;
        for(int i: energy){
            sum+=i;
        }
        int maxSum=maxSubArraySum(energy);
        int minSum=minSubArraySum(energy);
        int wrappedDifference=sum-minSum;
        if(maxSum<0) return maxSum;
        return Math.max(maxSum,wrappedDifference);
        
    }
    
    public static int maxSubArraySum(int[] energy){
        int sum=0,maxSum=energy[0];
        for(int i:energy){
            sum+=i;
            if(sum>maxSum){
                maxSum=sum;
            }
            if(sum<0) sum=0;
        }
        return maxSum;
    }
    
    public static int minSubArraySum(int[] energy){
        int sum=0,minSum=energy[0];
        for(int i:energy){
            sum+=i;
            if(sum<minSum) minSum=sum;
            if(sum>0) sum=0;
        }
        return minSum;
    }

    
    

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] energy = new int[n];
        for (int i = 0; i < n; i++) {
            energy[i] = sc.nextInt();
        }
        System.out.println(maxCircularEnergy(energy));
    }
}

```

## Output:

<img width="405" height="229" alt="image" src="https://github.com/user-attachments/assets/11ca4a91-fbc6-4f23-8eb3-0dcbe2393599" />


## Result:
The program successfully Implemented and the output is verified. 
