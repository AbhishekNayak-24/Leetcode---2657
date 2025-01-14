# Leetcode---2657
Find the Prefix Common Array of Two Arrays
// code in java
import java.util.HashSet;

public class Solution {
    public int[] findThePrefixCommonArray(int[] A, int[] B) {
        int n = A.length;
        int[] result = new int[n];
        HashSet<Integer> seen = new HashSet<>();
        int commonCount = 0;

        for (int i = 0; i < n; i++) {
            // Add elements of A[i] and B[i] to the set
            if (seen.contains(A[i])) {
                commonCount++;
            } else {
                seen.add(A[i]);
            }

            if (seen.contains(B[i])) {
                commonCount++;
            } else {
                seen.add(B[i]);
            }

            // Store the common count for the current prefix
            result[i] = commonCount;
        }

        return result;
    }

    // Test the function
    public static void main(String[] args) {
        Solution solution = new Solution();
        int[] A = {1, 3, 2, 4};
        int[] B = {3, 1, 2, 4};
        int[] result = solution.findThePrefixCommonArray(A, B);
        
        // Print the result
        for (int num : result) {
            System.out.print(num + " ");
        }
    }
}
