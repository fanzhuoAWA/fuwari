---
title: Binary Search Template
published: 2025-05-24
description: zzz
tags: [C++, Binary Search, Template]
image: "https://image.fanzhuo.xyz/file/AgACAgUAAyEGAASKws10AAMSaDGu__uKwFRpuBqE1JK6c0PXTiMAAuXJMRvLa4hVGXYdQrPWg50BAAMCAANtAAM2BA.png"
category: Algorithm
draft: false
---

Some notes taken during class.

```cpp
// Integer binary search
int L = 0, R = 1e9;
int ans = -1;
while (L <= R) {
    int mid = (L + R) >> 1;
    if (check(mid)) {
        ans = mid;
        R = mid - 1;
    } else {
        L = mid + 1;
    }
}

// Real number binary search or floating-point binary search
long double l = 0, r = 1e9;
int T = 100;
while (T--) {
    long double mid = (l + r) * 0.5;
    if (check(mid)) {
        l = mid;
    } else {
        r = mid;
    }
}
cout << l << "\n"; // Outputting 'r' is also acceptable

// Binary search functions
// lower_bound(*begin, *end, val, cmp) // cmp is a custom comparison function (optional, not recommended to use)
// upper_bound()

// lower_bound: Under the given sorting rule, finds the first pointer to a value greater than or equal to 'val'
// upper_bound: Under the given sorting rule, finds the first pointer to a value greater than 'val'

// Example:
int a[50];
a[1] = 2;
a[2] = 4;
a[3] = 5;
a[4] = 6;
auto it = lower_bound(a + 1, a + 49, 5);
cout << *it << "\n"; // Outputs 5 (a[3]), actually obtains the position of the first value greater than or equal to the required value (val = 5)

// Access the first value greater than or equal to 'val'
// Second usage method:
int pos = lower_bound(a + 1, a + 49, 5) - a; // Obtains the desired position
// a[pos] == *it
```