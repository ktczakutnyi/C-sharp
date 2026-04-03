# Find the odd int

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

 ```
for each number
  count how many times it(the number) appears
  if the count is odd
    reaturn it
```

# method 2
**O(n) done by using XOR**
```
Public Static int find_it(int[] seq)
{
  int result = 0;
  foreach (int num in seq)
  {
    result ^= num;
  }
  return result;

}
```
**O(n) done by using XOR**

# *Let's brake down EVERYTHING* 

## Why it works (think in binary terms)
- a num xor itself becomes 0
- a num xor 0 stays the same
- therefor even number cancels itself out
- example 3^5 3=0011 5=0101 0011^0101=0110 011=6 so 3^5=6
- **rule 1** a^a=0 a# xor itself = 0
- **rule 2** a^0=a a# xor 0 stays the samee
- Example: 7^0=7 2^0=2 7^7=0 2^2=0
- why it cancels out: {1,1,2} start result =0 0^1=1 1^1=0 0^2=2

```
function find_it(sequence)
  set result to 0 (creating the varible)
  for each number in sequence
    result = rsult XOR number
  End for
  return result
end functon
```

## 1. Method Declaration
   `Public Static int find_it(int[] seq)` - This line defines a function (method)

  - `Public` - This means any code can call this method. Not restricted to the class. "This funtion is visible to the outside world"

  - `Static` - means the function belongs to the class itself, not an of the class. Example: `Math.Abs(5)` we didnt create a math object, we only called it. Similar to an import in python

  - `int` - stands for integer. it means a whole number. this is the return type. it tells c# "This function will return an int"

  - `find_it` - this is the methods name. tbh it could be anything. But people like it to kinda make sence and be readable

  - `(int[] seq)` - this is parameter (input)

  - Example call: find_it(new int[] {1,1,2,2,3,3,3};

## 2. Create the start varible
`int result = 0` - this creates a varible named resule and starts it at 0. this will hold the runnint xor resilt

## 3. loop through each number in the arry one at a time
`foreach(int num in seq)` - this means go through each number in the arry one at a time. 

## 4. XOR the result
`reult^=num;` -  result=result^num; so each time through the loop we combine the current number into the result

## 5. return whats left
`return result;` - after all the even count numbers cancle out the odd number is the only one left. Example [1,2,2,3,3,4,3,3,3,2,2,1] each numver group becomes 0 0^0^0^4=4 


