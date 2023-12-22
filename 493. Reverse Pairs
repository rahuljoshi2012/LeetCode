class Solution {
    public int reversePairs(int[] nums) {
        // base case
        if (nums.length <= 1) {
            return 0;
        }
        // divide and conquer
        int[] leftArray = Arrays.copyOfRange(nums, 0, nums.length / 2);
        int[] rightArray = Arrays.copyOfRange(nums, nums.length / 2, nums.length);
        int left = reversePairs(leftArray);
        int right = reversePairs(rightArray);
        Arrays.sort(leftArray);
        Arrays.sort(rightArray);
        int cross = countCrossInversions(leftArray, rightArray);
        return left + right + cross;

    }

    private int countCrossInversions(int[] num1, int[] num2) {
        int count = 0;
        int i = 0, j = 0; // two pointers
        while (i < num1.length && j < num2.length) {
            if (isReverse(num1[i], num2[j])) {
                // we find all inversions with num2[j], hence need to move j
                count += (num1.length - i);
                j++;
            } else {
                i++;
            }
        }
        return count;
    }

    private boolean isReverse(int a, int b) {
        return (a % 2 == 0) ? a / 2 > b : (a - 1) / 2 >= b;
    }
}

// Time Complexity O(N*logN*logN)
// Space Complexity O(N)
