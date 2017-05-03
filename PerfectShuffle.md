## Another post

Given an array of size 2n, write a method to do perfect shuffle on it.

```java
import java.util.Arrays;

public class PerfectShuffle {
    public int[] shuffle(int []input) {
        if (input == null || input.length % 2 != 0) {
            throw new IllegalArgumentException();
        }

        if (IsPowOfX.isPow(input.length, 2)) {
            // If power of 2 - we could do more efficiently.
            return efficientCase(input);
        } else {
            // General O(n^2) solution.
            return generalCase(input);
        }
    }

    /**
     * @param input
     * @return
     */
    private int[] generalCase(int []input) {
        int i = 1, j = input.length/2;
        while (i < j) {
            int temp = input[j];
            move(input, i, j);
            input[i] = temp;
            i = i + 2;
            j++;
        }
        return input;
    }

    /**
     * @param input
     * @return
     */
    private int[] efficientCase(int []input) {
        
        return input;
    }

    private void swapMidArray(int []input, int start, int end) {
        
    }

    private void move(int []input, int start, int end) {
        for (int index = end; index > start; index--) {
            input[index] = input[index-1];
        }
    }

    public static void main(String[] args) {
        int []input = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
        PerfectShuffle obj = new PerfectShuffle();
        System.out.println(Arrays.toString(input));
        obj.shuffle(input);
        System.out.println(Arrays.toString(input));
    }
}
```
