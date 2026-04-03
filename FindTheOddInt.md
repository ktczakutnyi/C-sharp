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
Public Static int find_it(int[] seq)
{
  foreach (int num in seq)
    {int count = 0;
      foreach (int n in seq)
      {if (n == num)
        {count++;}
      }
      if (count%2 == 1)
        {return num;
        }}
  return -1; 
  
}
```

**This is O(n^2)**

# *Let's brake down EVERYTHING* 

## 1. Method Declaration
   `Public Static int find_it(int[] seq)` - This line defines a function (method)

  - `Public` - This means any code can call this method. Not restricted to the class. "This funtion is visible to the outside world"

  - `Static` - means the function belongs to the class itself, not an of the class. Example: `Math.Abs(5)` we didnt create a math object, we only called it. Similar to an import in python

  - `int` - stands for integer. it means a whole number. this is the return type. it tells c# "This function will return an int"

  - `find_it` - this is the methods name. tbh it could be anything. But people like it to kinda make sence and be readable

  - `(int[] seq)` - this is parameter (input)

## 2. for each loop
`foreach(int num in seq)` - this loops through every integer (whole number) in the arry 

## 3. Count verible
`int count = 0;` - this creates an integer called count that stores how many times a number appears. Example `count=0` now every time that cumber apereas count++ or count=count+1

## 4. Second (nested) loop counting
`foreach(int n in seq` - this loops through the array again. and compares every element to `num` example num=3 1,2,2,3 (match), 3(match)  

## 5. Check if matches
`if(n==num)` - checks if n equals num if yes `count++` os count= count +1

## 6. check if number appears even or odd number of times
`it(count%2==1)` -  divides by 2 and then sees what ramander is. if truw returns answer

## 7. answer
`return num` - this returns the value of num 

## 8. saftey return
`return =1` - this is a back up return **C# REQUIRES EVERY CODE PATH TO RETURN TO SOMETHING**

## Walkthrough
- 1. input. [0,1,0,1,0]
- 2. loop through seq counts 0 is 3 times 1 is 2 times
- 3. check if its odd: 3%2=1 = odd so returns the number `0` because it appears an odd amount of times (3 times)

# method 2
**O(n) done by using XOR**
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
