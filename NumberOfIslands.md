#Daily Temperatures

Given an array of integers temperatures represents the daily temperatures, return an array answer such that answer[i] is the number of days you have to wait after the ith day to get a warmer temperature. If there is no future day for which this is possible, keep answer[i] == 0 instead.

Example 1:
```
Input: temperatures = [73,74,75,71,69,72,76,73]
Output: [1,1,4,2,1,1,0,0]
Example 2:
```
```
Input: temperatures = [30,40,50,60]
Output: [1,1,1,0]
Example 3:
```
```
Input: temperatures = [30,60,90]
Output: [1,1,0]
 ```

Tags: *Array, Stack, Monotonic Stack*
> Source https://leetcode.com/problems/daily-temperatures/description/

```
Public Static 
{
  
}
```

**This is O)**

# *Let's brake down EVERYTHING* 

## 1. Method Declaration
   `Public Static int find_it(int[] seq)` - This line defines a function (method)

  - `Public` - This means any code can call this method. Not restricted to the class. "This funtion is visible to the outside world"

  - `Static` - means the function belongs to the class itself, not an of the class. Example: `Math.Abs(5)` we didnt create a math object, we only called it. Similar to an import in python

  - `int` - stands for integer. it means a whole number. this is the return type. it tells c# "This function will return an int"

  - `find_it` - this is the methods name. tbh it could be anything. But people like it to kinda make sence and be readable

  - `(int[] seq)` - this is parameter (input)

## 2.
`foreach(int num in seq)` - 

## 3. 
`int count = 0;` - 

## 4.
`foreach(int n in seq` -   

## 
`if(n==num)` - 

## 6.
`it(count%2==1)` - 

## 7. 
`return num` -  

## 8. 
`return =1` -

## Walkthrough
- 1. 
- 2. 
- 3. 

 ```
for each number
  count how many times it(the number) appears
  if the count is odd
    reaturn it
```
