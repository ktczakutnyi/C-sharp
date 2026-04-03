# Multiples of 3 or 5

Given an array of integers, find the one that appears an odd number of times.

There will always be only one integer that appears an odd number of times.

Examples

[7] should return 7, because it occurs 1 time (which is odd).

[0] should return 0, because it occurs 1 time (which is odd).

[1,1,2] should return 2, because it occurs 1 time (which is odd).

[0,1,0,1,0] should return 0, because it occurs 3 times (which is odd).

[1,2,2,3,3,3,4,3,3,3,2,2,1] should return 4, because it appears 1 time (which is odd).

Tags: *Fundamentals*
> Source https://www.codewars.com/kata/54da5a58ea159efa38000836 

# There are two diffrent ways to this that we will cover 
# method 1
```
Public Static int solution (int value)
{
  
}
```

**This is O**

# *Let's brake down EVERYTHING* 

## 1. Method Declaration
   `Public Static int solution (int value)` - This line defines a function (method)

  - `Public` - This means any code can call this method. Not restricted to the class. "This funtion is visible to the outside world"

  - `Static` - means the function belongs to the class itself, not an of the class. Example: `Math.Abs(5)` we didnt create a math object, we only called it. Similar to an import in python

  - `int` - stands for integer. it means a whole number. this is the return type. it tells c# "This function will return an int"

  - `solution` - this is the methods name. tbh it could be anything. But people like it to kinda make sence and be readable

  - `(int value)` - this is parameter (input). solution(10) inside the function *value = 10*

## 2. 
`if (value < 0) return 0;` - 

## 3. 
`int sum = 0` - 

## 4. 
`for (int i = 0; i < value; i++)` -  

## 5. 
`if (i% 3 == 0 || i % 5 == 0)` - 

## 6. 
`%` - 


## 7. 
`||` -

## 8.
`sum += i` -

## 9. 
`return sum;` -

## Walkthrough
- 1. 
- 2. 
- 3. 
- 4. 
- 5. 

# method 1
```
Public Static int solution (int value)
{
  
}
```
**This is O**

# *Let's brake down EVERYTHING* 

## 1. Method Declaration
   `Public Static int solution (int value)` - This line defines a function (method)

  - `Public` - This means any code can call this method. Not restricted to the class. "This funtion is visible to the outside world"

  - `Static` - means the function belongs to the class itself, not an of the class. Example: `Math.Abs(5)` we didnt create a math object, we only called it. Similar to an import in python

  - `int` - stands for integer. it means a whole number. this is the return type. it tells c# "This function will return an int"

  - `solution` - this is the methods name. tbh it could be anything. But people like it to kinda make sence and be readable

  - `(int value)` - this is parameter (input). solution(10) inside the function *value = 10*

## 2. 
`if (value < 0) return 0;` - 

## 3. 
`int sum = 0` - 

## 4. 
`for (int i = 0; i < value; i++)` -  

## 5. 
`if (i% 3 == 0 || i % 5 == 0)` - 

## 6. 
`%` - 


## 7. 
`||` -

## 8.
`sum += i` -

## 9. 
`return sum;` -

## Walkthrough
- 1. 
- 2. 
- 3. 
- 4. 
- 5. 
