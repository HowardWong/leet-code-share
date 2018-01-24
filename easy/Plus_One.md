#Plus One

Given a non-negative integer represented as a non-empty array of digits, plus one to the integer.

You may assume the integer do not contain any leading zero, except the number 0 itself.

The digits are stored such that the most significant digit is at the head of the list.


----

```javascript
const plusOne = digits => {
    let need_add = true;
    let current_index = digits.length - 1;
    let before_computed, computed;
    
    do {
        if(current_index === -1) {
            digits.unshift(1);
            need_add = false;
            break;
        }
        before_computed = digits[current_index];
        if(before_computed === 9) {
            digits[current_index] = 0;
            current_index--;
        }else {
            digits[current_index]++;
            need_add = false;
        }
    } while(need_add)
    return digits;
};
```