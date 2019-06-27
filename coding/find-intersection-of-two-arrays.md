### Given
Given 2 arrays return their intersection (set intersection).



### Solution
There are two cases with arrays sorted and unsorted.

#### Intersection of sorted Arrays
Since the input arrays are already sorted, we could use iterate through each together and look for common elements.

```java
public int[] intersect(int[] nums1, int[] nums2) {
    if (nums1 == null || nums2 == null) return new int[]{};

    List<Integer> result = new ArrayList<>();
    int i = 0, j = 0;
    while (i < nums1.length && j < nums2.length) {
        if (nums1[i] < nums2[j]) {
            i++;
        } else if (nums1[i] > nums2[j]) {
            j++;
        } else {
            // Found common elements, add to the result list.
            result.add(nums1[i]);
            i++;j++;
        }
    }
    // Better way to do in Java?
    int[] ret = new int[result.size()];
    for (int idx = 0; idx < result.size(); idx++) {
        ret[idx] = result.get(idx);
    }
    return ret;
}
```

#####Interesection of unsorted arrays
* Method-1: We could sort the arrays and do it like above.
* Method-2: Use Hashtable to keep counts and find intersection through that.
