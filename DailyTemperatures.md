# Daily Temperatures

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

# There are two diffrent ways to this that we will cover 
# method 1 Monotonic Stack
```
Public int[] DailyTemperatures(int[] temperatures)
{
  int n=temperatures.Length;
  int[] answer= new int[n];
  for(int i=0; i<n; i++)
  {
    while(stack.count > 0 && temperatures[i]>temperatures[stack.peek()])
    { int prevIndex = stack.pop();
      answer[prevIndex = i-prevIndex;
     } stack.push(i);
   return answer;
   }
}
```
```
function DailyTemperatures(temperatures)
  n=length of temperatures arry
  create arry answer of size n
  create empty stack
  for i from 0 to n-1
   while stack is not empty
    and termperatures[i]>termperatures[top of stack]
    prev index x = pop from stack
    ianswer[prevIndex = i - previnex]
   push i onto stack
  return answer
```

**This is O(n)**

# *Let's brake down EVERYTHING* 

## 1. Method Declaration
   `Public Static int find_it(int[] seq)` - This line defines a function (method)

  - `Public` - This means any code can call this method. Not restricted to the class. "This funtion is visible to the outside world"

  - `int[]` - array of integers/whole numbers

  - `DailyTemperatures` - this is the methods name. tbh it could be anything. But people like it to kinda make sence and be readable

  - `(int[] temperatures)` - this is parameter (input) Example `Input: temperatures = [73,74,75,71,69,72,76,73]`

## 2.Get input arry length
`int n= temperature.length` - this makes an arry that stores the amount of days. example termpratures[73,74,75,71,79] n=5 

## 3. creat the arry answer
`int[] answer=new int[n];` - creates an arry named answer that is the size of n anf pre fill it with 0s. this creates an arry names answer with an intial value of [0,0,0,0,0,0] 

## 4. Create the stack
`Stack<int> stack = new Stack<int>();` - this creates an empty stack that will store indexs of days waiting for warmer temp. Example stack [2,3,4] these are indexs of days waiting for warmer temps. not temps themselves because we need to calculate `days waited= index-prev index`  

## 5. loop through each day
`for(int i i=0; i<n; i++)` - for i from 0 to n-1 thi loops through every temp. example i=0, i=1. i=2... where temperatures[i]  

## 6. check solves (warmer) than earlier days
`while (stack.Count > 0 && temperatures[i] > temperatures[stack.Peek()])` - while stack is not empty and temperatures[i]>temperatures[top os stack]. 

this checks 2 conditions 
 - that the stack is not empty
 - todays temp is > than prev temp. "today is warmer than the day we were waiting for"

## 7. Pop the previous day
`int prevIndex = stack.Pop();` - this removes the top element from the stack. example stack[2,3,4] pop 3 stack=[2,3]  

## 8. calculate wait time (how many days)
`answer[prevIndex] = i - prevIndex` - example prevIndex=4 i=5 then answer[4]=5-4 answer[4]=1 meaning day4 you waited 1 day for warmer weather. think jumps. 

## 9. Push the surrent day
`stack.Push(i)` push i onto stack. if todays temp did not solve some future day yet, store it. example stac[2,3] push 5 stck[2,3,5] this means day 5 still needs answer day (warmer day) in the futures

## 10. reurn
`return answer` - returns the result after checking all the temps it returns the answer arry

## Walkthrough Example
## Walkthrough Example

- **1. input** `[73,74,75,71]`
- **2. start** `stack = [] answer = [0,0,0,0]`
- **3. day 0 temperature = 73** stack is empty, so push the index. `push 0` `stack = [] answer = [0,0,0,0]`
- **4. day 1 temperature = 74** Check if today is warmer than the day on top of the stack. 74 > 7 This is true, so resolve the earlier day. `pop 0; answer[0] = 1 - 0 = 1; push 1`
 Result: `stack = [1] answer = [1,0,0,0]`
- **5. day 2  temperature = 75** Check: 75 > 74 True , so resolve the previous day. `pop 1; answer[1] = 2 - 1 = 1; push 2`
Result: `stack = [2] answer = [1,1,0,0]`
- **6. day 3 temperature = 71** Check: 71 < 75 Not  True (warmer), this day must wait. `push 3`
Result: `stack = [2,3] answer = [1,1,0,0]`
- **7. loop ends** Days `2` and `3` never find a warmer future temperature. Their answers remain `0`.
- **Final answer** `[1,1,0,0]`

The stack stores: `indexes of days still waiting for a warmer temperature`

When a warmer day appears:
```
pop old days
calculate wait time
store the answer
```

Then push the current day:
```
push current index onto the stack
```

---

### Mental Model

Think of the stack as:

```
"days still waiting for a warmer temperature"
```

When a warmer day arrives, those waiting days are **resolved immediately**.

# method 2 Brute-Force
```
Public int[] DailyTemperatures(int[] temperatures)
{

}
```
```

```

**This is O**

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
