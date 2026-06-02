
# EX 1C Valid Pairs using Brute Force Approach
## DATE:17/04/2026
## AIM:
To write a Java program to for given constraints.
Given an integer array nums and an integer k, return the number of pairs (i, j) where i < j such that |nums[i] - nums[j]| == k.

The value of |x| is defined as:

x if x >= 0.
-x if x < 0.

## Algorithm
1.Start the program.

2.Input the size of the array n, the n array elements, and an integer k.

3.Initialize a counter variable count = 0.

4.Compare each pair of elements:

Use two loops:
For each i from 0 to n-1,
and for each j from i+1 to n-1,
check if the absolute difference |nums[i] - nums[j]| == k.

If true, increment count by 1.

5.Display the total count of such pairs and stop the program. 

## Program:
```
/*

Developed by: Ananda Rakshan K V
Register Number:  212223230014
*/
import java.util.Scanner;
public class CountPairsWithDifference {
    public static int countKDifference(int[] nums, int k) {
        int count=0;

        HashMap<Integer,Integer> map=new HashMap<>();

        for(int i:nums){
            if(map.containsKey(i-k)){
                count+=map.get(i-k);
            }

             if(map.containsKey(i+k)){
                count+=map.get(i+k);
            }

            if(!map.containsKey(i)){
                map.put(i,1);

            }
            else{
                map.put(i,map.get(i)+1);
            }
        }

        return count;
    }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] nums = new int[n];
        for (int i = 0; i < n; i++) {
            nums[i] = sc.nextInt();
        }
        int k = sc.nextInt();
        int result = countKDifference(nums, k);
        System.out.println(result);
        sc.close();
    }
}

```

## Output:

<img width="396" height="290" alt="image" src="https://github.com/user-attachments/assets/71cc1b06-d4e6-422a-8707-63a95b3a879b" />

## Result:
The program successfully implemented and the expected output is verified.
