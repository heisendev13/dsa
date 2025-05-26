# Kadane's Algorithm – Maximum Subarray Sum

This repository contains my implementation and understanding of **Kadane's Algorithm**, a powerful dynamic programming technique used to find the **maximum sum of a contiguous subarray** within a one-dimensional array of numbers.

---

## 📌 What is Kadane's Algorithm?

Kadane’s Algorithm is used to solve the **Maximum Subarray Problem** with a linear time complexity of **O(n)**. It iteratively computes the maximum subarray sum ending at each position and keeps track of the global maximum.

---

## 📚 Problem Statement

> Given an array `arr[]` of integers, find the **contiguous subarray** (containing at least one number) which has the largest sum and return its sum.

---

## ✅ Approach – Kadane's Algorithm

- Initialize two variables:
  - `max_so_far = arr[0]`
  - `max_ending_here = arr[0]`
- Loop from index 1 to n-1:
  - Update `max_ending_here = max(arr[i], max_ending_here + arr[i])`
  - Update `max_so_far = max(max_so_far, max_ending_here)`
- Return `max_so_far`

---

## 💡 Intuition

- At each step, decide whether to **extend the previous subarray** or **start a new subarray** with the current element.
- If the current element is greater than the current subarray sum + current element, we start fresh from here.

---

## 🧠 Pseudocode

```plaintext
class Solution {
    public int maxSubArray(int[] nums) {
        int currsum=nums[0];
        int maxsum=nums[0];
        for(int i=1;i<nums.length;i++){
            if(currsum<0){
                currsum=nums[i];
            }
            else{
                currsum+=nums[i];
               
            }
            maxsum=Math.max(maxsum,currsum);
        }
        return maxsum;
    }
}
