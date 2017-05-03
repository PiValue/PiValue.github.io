## Problem
Given numbers x and y, check if y is a power of x.

## What to consider
TODO - update later.

## Solution
```java

public class IsPowOfX {
    public static boolean isPow(int input, int x) {
        if (input < 0) return false;
        if (x == 1) return (input == 1);

        int pow = 1;
        while (pow < input) {
            pow = pow * x;
        }
        return (pow == input);
    }
}
```

## Complixity
Update later
