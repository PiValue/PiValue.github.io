## Problem
Given a matrix with integers - if an element is zero, make its row and column zero.

## What to consider
* This could be done without extra memory.

## Solution
```java
import java.util.Arrays;

// In-place solution.
public class ZeroOutMatrix {
    public void zeroOutMatrix(int [][]matrix) {
        if (matrix == null || matrix[0].length == 0) {
            return;
        }

        printMatrix(matrix, "Before:: ");
        // Since [0][0] is shared between row and column, have separate column.
        boolean shouldRowBeZeroed = false;
        boolean shouldColumnBeZeroed = false;
        for (int i = 0; i < matrix.length; i++) {
            for (int j = 0; j < matrix[i].length; j++) {
                if (matrix[i][j] != 0) {
                    continue;
                }
                shouldColumnBeZeroed = (shouldColumnBeZeroed) || (j == 0);
                shouldRowBeZeroed = (shouldRowBeZeroed) || (i == 0);
                matrix[i][0] = 0;
                matrix[0][j] = 0;
            }
        }
        // Check what rows have first element marked zero.
        for (int row = 1; row < matrix.length; row++) {
            if (matrix[row][0] == 0) makeRowZero(row, matrix);
        }
        // Check what columns have first element marked zero.
        for (int col = 1; col < matrix[0].length; col++) {
            if (matrix[0][col] == 0) makeColumnZero(col, matrix); 
        }
        // Take care of first row and column that need to be zero.
        if (shouldColumnBeZeroed) makeColumnZero(0, matrix);
        if (shouldRowBeZeroed) makeRowZero(0, matrix);
        printMatrix(matrix, "After:: ");
    }

    /**
     * Helper method to zero-out a given column.
     * */
    private void makeColumnZero(int column, int[][] matrix) {
        for (int []row : matrix) {
            row[column] = 0;
        }
    }

    /**
     * Helper method to zero-out a given row.
     * */
    private void makeRowZero(int row, int [][]matrix) {
        for (int col = 0; col < matrix[row].length; col++) {
            matrix[row][col] = 0;
        }
    }

    /**
     * Helper method to print given matrix.
     * */
    private void printMatrix(int [][]matrix, String message) {
        if (message != null) System.out.println(message);
        for (int []row : matrix) {
            System.out.println(Arrays.toString(row));
        }
    }

    public static void main(String[] args) {
        int [][]matrix = {
                            {0, 2, 3, 4, 5},
                            {1, 2, 3, 4, 5},
                            {1, 2, 3, 0, 5},
                            {1, 2, 3, 4, 5},
                            {1, 2, 3, 4, 5},
                            {1, 2, 3, 4, 5}};
        ZeroOutMatrix obj = new ZeroOutMatrix();
        obj.zeroOutMatrix(matrix);
    }
}
```
