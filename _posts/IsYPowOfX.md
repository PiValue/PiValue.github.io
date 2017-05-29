---
layout: post
title: Write a functions to check if y is a power of x.
category: Coding
tags: [math, leetcode]
---

## Problem
Given numbers x and y, write a method to check if y is a power of x.

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
