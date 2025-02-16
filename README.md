# Plus-One
Given a non-empty array of decimal digits representing a non-negative integer, increment one to the integer.

The digits are stored such that the most significant digit is at the head of the list, and each element in the array contains a single digit.

You may assume the integer does not contain any leading zero, except the number 0 itself.

 

_Example 1:_

Input: digits = [1,2,3]

Output: [1,2,4]

Explanation: The array represents the integer 123.

_Example 2:_

Input: digits = [4,3,2,1]

Output: [4,3,2,2]

Explanation: The array represents the integer 4321.

_Example 3:_

Input: digits = [0]

Output: [1]
 

_Constraints:_

1 <= digits.length <= 100

0 <= digits[i] <= 9


# Solution:

_First method:_

```
var plusOne = function(digits) {

    let carry = true
    for (let i = digits.length - 1; i >= 0; i -= 1) {
        if (digits[i] === 9 && carry) {
            digits[i] = 0;
            if (i === 0) {
                digits.unshift(1);
                break;
            }
        } else if (carry) {
            digits[i] += 1;
            carry = false;
        }
    }
    return digits;
}
```


_Second method:_

```
var plusOne = function(digits) {

    return String(BigInt(digits.join('')) + BigInt(1)).split('')
}
```
