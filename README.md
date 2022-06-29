# leetcode_palindrome_Number
+ 숫자가 대칭인지 확인
+ 判斷input是否是對稱

-----
+ Example1
```
Input: x = 121
Output: true
Explanation: 121 reads as 121 from left to right and from right to left.
```
----
+ Example2
```
Input: x = -121
Output: false
Explanation: From left to right, it reads -121. From right to left, it becomes 121-. Therefore it is not a palindrome.
```
----
+ Example3
```
Input: x = 10
Output: false
Explanation: Reads 01 from right to left. Therefore it is not a palindrome.
Since 4193 is in the range [-231, 231 - 1], the final result is 4193.
```
----
```python
class Solution:
    def isPalindrome(self, x: int) -> bool:
        strings = str(x) # int를 string으로 전환
        reversed_str = strings[::-1] # 비교할 reverse 만들기
        return (strings == reversed_str) # 둘이 같다면 대칭 아니면 비대칭
```
---
### More short code
```python
class Solution:
    def isPalindrome(self, x: int) -> bool:
        return (str(x) == str(x)[::-1]) # One line
```
### another answer 2 it's so slow
```python
from collections import deque # use deque library
class Solution:
    def isPalindrome(self, x: int) -> bool:
        check = 0 # check it is True or False
        if x < 10 and x >=0: 
            return(True)
        elif x >= -2*31 and x <= 2**31-1:
            num = str(x)
            deq = deque(num)

            while True: # Use deque method popleft() and pop() to check each sides are same or not
                try:
                    left = deq.popleft()
                    right = deq.pop()
                    if left == right: 
                        check = 1
                    else:
                        check = 0
                        break
                except: # Prevent Error for popleft() and pop() methods
                    break
            if check == 1:
                return(True)
            else:
                return(False) 
        else:
            return(False)
```
### another answer 3 it's soooooooooooooooo slow
```python
class Solution:
    def isPalindrome(self, x: int) -> bool:
        strings = str(x)
        reversed_str = "".join(reversed(strings)) # 다른 reverse 방법
        return (strings == reversed_str)
```
```
결론 :
이번건 난이도 Easy답게 엄청 쉬웠다
```
---
```
結論:
這次忽然體驗到難易度明顯下降
```
---
### Result
Runtime: 66 ms, faster than 88.86% of Python3 online submissions for Palindrome Number.\
Memory Usage: 13.8 MB, less than 58.94% of Python3 online submissions for Palindrome Number.

