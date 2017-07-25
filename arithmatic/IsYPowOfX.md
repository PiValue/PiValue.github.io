## Problem
Given numbers x and y, check if y is a power of x.

## What to consider
TODO - update later.

## Solution
```java
public class IsPowOfX {
    public static boolean isPow(int y, int x) {
        if (y < 0) return false;
        if (x == 1) return (y == 1);

        int pow = 1;
        while (pow < y) {
            pow = pow * x;
        }
        return (pow == y);
    }
}
```

## Complixity
Update later
