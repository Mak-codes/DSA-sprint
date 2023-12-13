Second Larget Element ->>>>

import java.util.* ;
import java.io.*; 
public class Solution {
	public static int findSecondLargest(int n, int[] arr) {
		// Write your code here.
		int large = Integer.MIN_VALUE;
		int secondLarge = Integer.MIN_VALUE;
		int temp = secondLarge;
		for(int i=0; i<n; i++){
			if(arr[i] > large){
				secondLarge = large;
				large = arr[i];
			} else if(arr[i] != large && arr[i] > secondLarge){
				secondLarge = arr[i];
			}
		}
		return (large==secondLarge || temp == secondLarge) ? -1: secondLarge;
	}
}

Rotate An Array By K ->>>>

import java.util.ArrayList;

public class Solution {
	public static ArrayList<Integer> rotateArray(ArrayList<Integer> arr, int k) {
        // Write your code here.
       ArrayList<Integer> second = new ArrayList<>();
        int j = 0;
        for (int i = 0; i < arr.size(); i++) {
            if (i + k < arr.size())
                second.add(arr.get(i + k));
            else {
                second.add(arr.get(j));
                j++;
            }
        }
        return second;
    }
}

Non-Decreasing Array ->>>>

import java.util.* ;
import java.io.*; 
public class Solution {
	public static boolean isPossible(int[] arr, int n) {
		// Write your code here.

		for (int i = 1, err = 0; i < arr.length; i++)
            if (arr[i] < arr[i-1])
                if (err++ > 0 || (i > 1 && i < arr.length - 1 && arr[i-2] > arr[i] && arr[i+1] < arr[i-1]))
                    return false;
        return true;
	}
}
