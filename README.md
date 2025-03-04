# march3_2025
The problem that i solved today in leetcode

1.You are given a 0-indexed integer array nums and an integer pivot. Rearrange nums such that the following conditions are satisfied:

Every element less than pivot appears before every element greater than pivot.
Every element equal to pivot appears in between the elements less than and greater than pivot.
The relative order of the elements less than pivot and the elements greater than pivot is maintained.
More formally, consider every pi, pj where pi is the new position of the ith element and pj is the new position of the jth element. If i < j and both elements are smaller (or larger) than pivot, then pi < pj.
Return nums after the rearrangement.

Code:
class Solution {
    public int[] pivotArray(int[] nums, int pivot) {
        int n=nums.length;
        List<Integer> small=new ArrayList<>();
        List<Integer> large=new ArrayList<>();
        List<Integer> equal=new ArrayList<>();
        for(int x:nums)
        {
            if(x>pivot)
                large.add(x);
            else if(x<pivot)
                small.add(x);
            else
                equal.add(x);
        }
        int i=0;
        for(int x:small)
            nums[i++]=x;
        for(int x:equal)
            nums[i++]=x;
        for(int x:large)
            nums[i++]=x;
        return nums;
    }
}
