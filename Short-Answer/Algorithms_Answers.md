#### Please add your answers to the **_Analysis of Algorithms_** exercises here.

## Exercise I

a)
<br>
`O(n^3)`
<br>
Because we are iterating over all values of `a` less than `n^3`, the number of operations performed will scale according to a cubic curve. For example, `n=1` will require `1` operation, `n=2` will require `8`, `n=3` will require `27`, and so on.

b)
<br>
`O(n*logn)`
<br>
The outer loop will have a runtime of `O(n)`. The inner loop will have a runtime of `O(logn)`, because the increment variable, `j`, is doubling each iteration. This has the same effect as the upper bound, `n`, being halved each iteration.

c)
<br>
`O(n)`
<br>
This function will perform exactly one recursive function call for every integer between `bunnies` and `0`. It's basically the same as having a single loop iterating from `0` to `bunnies`.

## Exercise II

This is a binary search problem, with a litle twist. In order to find `f`, we need to find either a floor where a dropped egg doesn't break _and_ an egg dropped from the floor immediately above does break, or the inverse.
<br>
<br>
We'll start by choosing the middle floor, which we'll call `m` (`m = n/2`). We'll drop an egg. If the egg dropped from floor `m` doesn't break, then we know we must be below `f`. We would then consider floor `m` our ground floor, and repeat the previous process, dividing the building in half, dropping an egg, and basing our next action on the results. If an egg dropped from `m` breaks, we would then consider `m` our new roof.
<br>
<br>
Eventually, our buidling will be divided in half until we've only got one floor left. We'll drop one more egg. If it breaks, then we are on floor `f`, so we'll return the value of `m`. If it doesn't break, that must mean we're one floor below `f`, so we'll return `m+1`.
The runtime complexity is `O(logn)`, because we are dividing the building in half each time. A building twice as tall as another will only require one more operation. Binary search is dope.
