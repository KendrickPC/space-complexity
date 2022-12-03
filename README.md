# Space Complexity

So far, we've been focusing on time complexity:
How can we analyze runtime of an algorithm as size of inputs increase?

We can also use big O notation to analyze space complexity:
How will memory usage scale as size of inputs increase?


# Rules of Thumb in JS:

- [x] Most primitives (booleans, numbers, undefined, null): constant space
For the most part, they all get allocated the exact same amount of space.

- [x] Strings: O(n) space (where n is the string length)
Strings are a bit different. A longer string will take up more space. 
So strings are O(n) complexity.
So as the number of characters n grows, the amount of storage/memory needed to store that string ALSO grows.

- [x] Reference types: generally O(n), where n is the length of array (or # of keys in an object).
An array of 1 item vs an array of 1000 items.
The 1000 items array would take roughly 1000x more space than the 1 item array.

## Example 1:

##### O(1) space
```js
function sum(nums) {
  // total variable is the one being STORED in memory...
  let total = 0;
  // This loop below doesn't really matter...
  for (let i=0; i<nums.length; i++>) {
    total += nums[i];
  }
  return total;
}
```
Above... time complexity is O(n), but space complexity O(1) because storing a number, regardless of the size of that number, takes up the same amount of space.
The above example is constant space O(1).

## Example 2:
##### O(n) space
```js
function double(nums) {
    let doubledNums = [];
    for (let i = 0; i< nums.length; i++) {
      doubledNums.push(2 * nums[i])
    }
    return doubledNums;
}
```
If we pass in a 10 items array, we are creating a NEW 10 items array. 
If we pass in a 10000 items array, we are creating a NEW 10000 items array.

The amount of space it takes to store an array grows roughly in proportion with the length of that array.


[Space-Time Tradeoff](https://simple.wikipedia.org/wiki/Space-time_tradeoff)

# Recap
To analyze performance of algorithm, use Big O Notation.
- Can give high level understanding of time or space complexity.
- Doesn't care about precision, only general trends (linear? quadratic? constant?)
- Depends only on algorithm, not hardware used to run code.

Big O Notation is everywhere. Get lots of practice. It's your vegetables of programming.
