# Single pound
## Double pound
## Double pound-2
### Third pound
### Third pound-2
Some data that is put in here. ```what is this``` **This is Bold**

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

    public static void main(String[] args) {
        System.out.println("Is 4 of 2^x: "   + IsPowOfX.isPow(4, 2));
        System.out.println("Is 5 of 2^x: "   + IsPowOfX.isPow(5, 2));
        System.out.println("Is 81 of 3^x: "  + IsPowOfX.isPow(81, 3));
        System.out.println("Is 100 of 2^x: " + IsPowOfX.isPow(100, 2));
        System.out.println("Is 128 of 2^x: " + IsPowOfX.isPow(128, 2));
        System.out.println("Is 625 of 5^x: " + IsPowOfX.isPow(625, 5));
        System.out.println("Is 256 of 4^x: " + IsPowOfX.isPow(256, 4));
        System.out.println("Is 40353608 of 7^x: " + IsPowOfX.isPow(40353608, 7));
        System.out.println("Is 40353607 of 7^x: " + IsPowOfX.isPow(40353607, 7));
    }
}

```
