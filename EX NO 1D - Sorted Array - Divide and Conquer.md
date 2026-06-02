
# EX 1D Sorted Array using Divide and Conquer Approach.
## DATE:17/04/2026

## AIM:
To write a Java program to for given constraints.
Given two sorted arrays nums1 and nums2 of size m and n respectively, return the median of the two sorted arrays.

The overall run time complexity should be O(log (m+n)).

## Algorithm
1.Start the program.
Read the sizes of two sorted arrays m and n, then input the elements of both arrays nums1 and nums2.

2.Initialize two pointers p1 = 0 and p2 = 0 to traverse both arrays.

3.Use a helper function getMin() to return the smaller of the current elements from both arrays and move the corresponding pointer forward.

4.Find the median:

If the total number of elements (m + n) is even, skip (m + n)/2 - 1 elements, then take the average of the next two smallest elements as the median.

If (m + n) is odd, skip (m + n)/2 elements, then take the next smallest element as the median.

5.Display the computed median and stop the program.
## Program:
```
/*
Program to implement  Sorted Array using Divide and Conquer Approach 
Developed by: Ananda Rakshan K V
Register Number:  212223230014
*/

import java.util.Scanner;

public class Solution {
   

    // Main logic to find median of two sorted arrays
    public double findMedianSortedArrays(int[] nums1, int[] nums2) {
        int n1=nums1.length;

        int n2=nums2.length;

        if(n1>n2){
            return findMedianSortedArrays(nums2, nums1);
        }

        int low=0,high=n1;

        int left=(n1+n2+1)/2;

        while(low<=high){
            int mid1=(low+high)/2;

            int mid2=left-mid1;

            int left1=Integer.MIN_VALUE,left2=Integer.MIN_VALUE;

             int right1=Integer.MAX_VALUE,right2=Integer.MAX_VALUE;

            if(mid1>0){
                left1=nums1[mid1-1];

            }

            if(mid2>0){
                left2=nums2[mid2-1];
            }

            if(mid1<n1){
                right1=nums1[mid1];
            }

            if(mid2<n2){
                right2=nums2[mid2];

            }

            if(right1>=left2 && right2>=left1){
                if((n1+n2)%2==0){
                    return (Math.max(left1,left2)+Math.min(right1,right2))/2.0;
                }
                else{
                    return (double)Math.max(left1,left2);
                }
            }
            else if(left1>right2){
                high=mid1-1;
            }
            else{
                low=mid1+1;
            }


        }

        return 0.0;
        
    }

    // Main method with user input
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        Solution sol = new Solution();

        // Input for nums1
        //System.out.print("Enter size of first sorted array: ");
        int m = sc.nextInt();
        int[] nums1 = new int[m];
        //System.out.println("Enter " + m + " sorted integers for first array:");
        for (int i = 0; i < m; i++) {
            nums1[i] = sc.nextInt();
        }

        // Input for nums2
        //System.out.print("Enter size of second sorted array: ");
        int n = sc.nextInt();
        int[] nums2 = new int[n];
        //System.out.println("Enter " + n + " sorted integers for second array:");
        for (int i = 0; i < n; i++) {
            nums2[i] = sc.nextInt();
        }

        // Find and display the median
        double median = sol.findMedianSortedArrays(nums1, nums2);
        System.out.println("Median of the two sorted arrays = " + median);
        
        sc.close();
    }
}
```

## Output:
<img width="883" height="330" alt="image" src="https://github.com/user-attachments/assets/d430c9c0-0455-4220-811f-1a6ab58b32f7" />

## Result:
The program successfully implemented and the expected output is verified.
