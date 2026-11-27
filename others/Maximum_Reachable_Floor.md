# **Maximum Reachable Floor Using Express Lifts**

## **1. Problem Statement**

You are inside a tall building containing 10⁹ floors, numbered from 1 to 10⁹, from bottom to top.

You are initially standing on **Floor 1**.

The building has `N` express lifts. Each lift connects exactly two distinct floors, represented by `Ai` and `Bi`.

Each lift has the following properties:

- It allows travel in both directions: from `Ai` to `Bi` and from `Bi` to `Ai`.
- It stops only at its two designated floors.
- It does not stop at any intermediate floors.

You cannot use stairs or walk between floors. You can travel only using the available lifts.

You can switch between lifts only when they share a common stopping floor.

**Your task is to determine the maximum-numbered floor you can reach, starting from Floor 1.**

## **2. Input Format**

- The first line contains an integer `N`, representing the number of lifts.
- Each of the next `N` lines contains two space-separated integers, `Ai` and `Bi`, representing the two floors connected by the `i-th` lift.

## **3. Output Format**

Print a single integer representing the maximum floor number reachable from Floor 1.

## **4. Constraints**

```
1 <= N <= 2 * 10⁵
1 <= Ai, Bi <= 10⁹
Ai != Bi
```

All input values are integers.

## **5. Sample Test Case 1**

**Input:**

```
4
1 4
4 3
3 10
5 20
```

**Output:**

```
10
```

**Explanation:**

Starting from Floor 1:

1. Take the first lift from Floor 1 to Floor 4.
2. Switch to the second lift and travel from Floor 4 to Floor 3.
3. Switch to the third lift and travel from Floor 3 to Floor 10.

Floor 20 is unreachable because the lift connecting Floors 5 and 20 has no connection to the lifts accessible from Floor 1.

Therefore, the maximum reachable floor is **10**.

## **6. Sample Test Case 2**

**Input:**

```
3
2 5
5 9
9 12
```

**Output:**

```
1
```

**Explanation:**

You start at Floor 1, but none of the lifts stops at Floor 1.

Therefore, you cannot board any lift, and you remain on Floor 1.

The maximum reachable floor is **1**.

## **7. Objective**

Find the highest floor reachable from Floor 1 using any valid sequence of lift journeys.

```
class Solution {

    public int maximumReachableFloor(int n, int[][] lifts) {

        // Solution goes here

    }

}
```