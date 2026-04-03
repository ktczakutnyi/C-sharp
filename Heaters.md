# Heaters

Winter is coming! During the contest, your first job is to design a standard heater with a fixed warm radius to warm all the houses.

Every house can be warmed, as long as the house is within the heater's warm radius range. 

Given the positions of `houses` and `heaters` on a horizontal line, return *the minimum radius standard of heaters so that those heaters could cover all houses*.

Notice that all the `heaters` follow your radius standard, and the warm radius will be the same.

Example 1:
```
Input: houses = [1,2,3], heaters = [2]
Output: 1
Explanation: The only heater was placed in the position 2, and if we use the radius 1 standard, then all the houses can be warmed.
```
Example 2:
```
Input: houses = [1,2,3,4], heaters = [1,4]
Output: 1
Explanation: The two heaters were placed at positions 1 and 4. We need to use a radius 1 standard, then all the houses can be warmed.
```
Examoke 3:
```
Input: houses = [1,5], heaters = [2]
Output: 3
 ```

Constraints:
 - 1 <= houses.length, heaters.length <= 3 * 104
 - 1 <= houses[i], heaters[i] <= 109


Tags: *Array, Stack, Monotonic Stack*
> Source https://leetcode.com/problems/heaters/description/
> similar tp https://codeforces.com/contest/702/problem/C#

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
