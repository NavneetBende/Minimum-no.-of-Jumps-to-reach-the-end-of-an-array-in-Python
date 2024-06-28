Minimum no. of Jumps to reach the end of an array in Python
On this page we will learn to create Minimum no. of Jumps to reach the end of an array in Python language. If not possible print -1.

Example:-

Input: arr = [1, 3, 5, 8, 9, 2, 6, 7, 6, 8, 9]
Output: 3 (1-> 3 -> 9 -> 9)
Explanation: Jump from 1st element to 2nd element as there is only 1 step, now there are three options 5, 8 or 9. If 8 or 9 is chosen then the end node 9 can be reached. So 3 jumps are required.
Python program for Minimum no. of Jumps to reach the end of an array

Explanation
Given an array of non-negative integers, Arr, of length N. You are initially positioned at the first index of the array. Each element in the array represents your maximum jump length at that position. Need to print the minimum number of jumps required to reach the last index. If it is not possible to reach the last index, print -1.

Algorithm
Initialize ans, i and set value zero
Run a while loop from range 0 to (length of array)-1
If i + arr[i] is less then length of arr
Increment value of ans by 1 and check if arr[i] is equal to 1
Increment value of i by arr[i]
Else increment the value of i with i minus index of max between arr index i + 1 to arr[i] + i + 1 of array arr
Else increment value of ans by 1 and value of i by arr[i]

Minimum no. of Jumps to reach the end of an array in Python
Python Code
Run
def jump(arr):
    ans = 0
    i = 0
    while i < len(arr) - 1:
        if i + arr[i] < len(arr):
            ans += 1
            if arr[i] == 1:
                i += arr[i]
            else:
                i += arr.index(max(arr[i + 1:arr[i] + i + 1])) - i
        else:
            ans += 1
            i += arr[i]

    return ans


arr = [1, 3, 5, 8, 9, 2, 6, 7, 6, 8, 9]
print("Minimum no of jumps required to reach end of the array : ", jump(arr))
Output
Minimum no of jumps required to reach end of the array : 3
