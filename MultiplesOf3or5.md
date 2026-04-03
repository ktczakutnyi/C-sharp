# Multiples of 3 or 5

Given an array of integers, find the one that appears an odd number of times.

There will always be only one integer that appears an odd number of times.

Examples

[7] should return 7, because it occurs 1 time (which is odd).

[0] should return 0, because it occurs 1 time (which is odd).

[1,1,2] should return 2, because it occurs 1 time (which is odd).

[0,1,0,1,0] should return 0, because it occurs 3 times (which is odd).

[1,2,2,3,3,3,4,3,3,3,2,2,1] should return 4, because it appears 1 time (which is odd).

Tags: *Mathematics, Algorithms*
> Source https://www.codewars.com/kata/54da5a58ea159efa38000836 

```
Public Static int solution (int value)
{
  if(value <0 )
    return 0;
  int sum=0;
  for (int i=0; i < value; i++)
    {if (i% 3 == 0 || i % 5 == 0)
      { 
      sum += i;
      }
    }
}
```

**This is O(n)**

# *Let's brake down EVERYTHING*

## 1. Method Declaration
   `Public Static int solution (int value)` - This line defines a function (method)

  - `Public` - This means any code can call this method. Not restricted to the class. "This funtion is visible to the outside world"

  - `Static` - means the function belongs to the class itself, not an of the class. Example: `Math.Abs(5)` we didnt create a math object, we only called it. Similar to an import in python

  - `int` - stands for integer. it means a whole number. this is the return type. it tells c# "This function will return an int"

  - `solution` - this is the methods name. tbh it could be anything. But people like it to kinda make sence and be readable

  - `(int value)` - this is parameter (input). solution(10) inside the function *value = 10*

## 2. Handeling the negative numbers
`if (value < 0) return 0;` - this checks for negatives because if a number is less than 0 it is negative. so it's kinda like a check point. It will only go down this branch if neg is true

## 3. Creating a verible to store the sum
`int sum = 0` - this creats a verable that is an integer named sum and sets it to 0. sum = the running total in this code

## 4. The loop
`for (int i = 0; i < value; i++)` -  this counts up from i while it is less to what ever value is set as. `for (start; condition; step)` in this case i = 0. `i++` is i=i+1 . If value = 10 then it will be 1,2,3,4,5,6,7,8,9 and will stop there because it is not <= .  

## 5. The condition
`if (i% 3 == 0 || i % 5 == 0)` - this checks is `i` is divisible by 3 or 5 

## 6. The modulus of factor `%`
`%` - example `a%b` means the remainder when `a` is divided by `b` `6%3=0` because 6/3=2 with no left over. `7%3=1` because 7/3=2 remainer 1.

why is works for moltiples: a num is a multiple when remainder is 0

## 7. Logical `||` operator
`||` - this is *or* `A||B` = A or B Binary - 10=1 01=1 00=0 11=1 Examples i=b 6%3=0 = true so we add 6 

## 8. Adding to the sum
`sum += i` - is the same as sum = sum + 1 , example sum=0 i=3 sujm=3 i=5 sum=8 i=6 sum=14

##9. returning the final answer
`return sum;` - `solution(10)` returns 23 walk through input: `solution(10)' numbers tested 0,1,2,3,4,5,6,7,8,9, multiples of 3 or 5: 3,5,6,9 sum: 3+5+6+9= 23

## Walkthrough
- 1. check with sum = 0
- 2. check every number nelow value (input)
- 3. check if its divisable by 3 or 5
- 4. add it to the sum
- 5. return final total  
