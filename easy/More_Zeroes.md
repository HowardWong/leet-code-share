# Move Zeroes

Given an array nums, write a function to move all 0's to the end of it while maintaining the relative order of the non-zero elements.

For example, given nums = [0, 1, 0, 3, 12], after calling your function, nums should be [1, 3, 12, 0, 0].

Note:
You must do this in-place without making a copy of the array.
Minimize the total number of operations.
Credits:
Special thanks to @jianchao.li.fighter for adding this problem and creating all test cases.


----

```javascript
const moveZeroes = nums => {
    const length = nums.length;
    let current_index = 0;
    let zero_count = 0;
    for(let i = 0; i < length; i++) {
        if(nums[i] !== 0) {
            nums[current_index] = nums[i];
            if(i !== current_index) {
                nums[i] = 0;
            }
            current_index++
        }
    }
};
```