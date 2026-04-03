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
```
for each day
while stack is not empty
and today is warmer than the day on top of the stack
pop the previous day
calculate how many days it waited
store that in the answer
push the current day onto the stack
```
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
Then push the current day: push current index onto the stack

### Mental Model

Think of the stack as:

```
"days still waiting for a warmer temperature"
```

When a warmer day arrives, those waiting days are **resolved immediately**.

#remeber
the stack stores `days that are still waiting for answer day` when warmer day appereas `pop earilier days and calculate waite and store`

# method 2 Brute-Force
```
public int[] DailyTemperatures(int[] temperatures)
{
    int n = temperatures.Length;
    int[] answer = new int[n];

    for (int i = 0; i < n; i++)
    {
        for (int j = i + 1; j < n; j++)
        {if (temperatures[j] > temperatures[i])
            {answer[i] = j - i;
                break;
            }
        }
    } return answer;
}
```

**O(n²)**
for each day you may scan all remaining days.

# *Let's brake down EVERYTHING* 

## 1. Method Declaration
   `Public Static int find_it(int[] seq)` - This line defines a function (method)

  - `Public` - This means any code can call this method. Not restricted to the class. "This funtion is visible to the outside world"

  - `int[]` - array of integers/whole numbers

  - `DailyTemperatures` - this is the methods name. tbh it could be anything. But people like it to kinda make sence and be readable

  - `(int[] temperatures)` - this is parameter (input) Example `Input: temperatures = [73,74,75,71,69,72,76,73]`

## 2. Get arry size
`int n = temperatures.Length;` - Stores how many elements are on the arry. example `[73,73,74] n=3` 

## 3. create answer arry
`int[] answer = new int[n];` -  this creates an arry the same size as `temperatuers` example start state `answer = [0,0,0,0,0]`

## 4. outer loop
`for (int i=0; i<n:i++)` - this selects the current day. example `i=0 i=1 i=2`   

## 5. inner loop
`for (int j = i+1; j<n;j++` - this scans for future days Example `currrent day = i , future day = j` 

## 6. compare temps
`if (temperatures[j] > temperatures[i])` - This checks: if the future day is warmer.

## 7. calcukate wait time
`answer [i] =j-i` - Example `i=2 j=6 6-2=4` so the wait is 4 days  

## 8. break
`break;` -Stops searching because found the first warmer day.

## Walkthrough
- **1. input** `[73,74,75,71]`
- **2. start** `answer = [0,0,0,0]
- **3. day 0 temperature = 73** check each future day: 74 > 73 = warmer
 store the wait time: `answer[0] = 1 - 0 = 1` result: `answer = [1,0,0,0]`
- **4. day 1 temperature = 74** check future days: 75 > 74 = warmer store wait time: `answer[1] = 2 - 1 = 1` result: `answer = [1,1,0,0]`
- **5. day 2 temperature = 75** check future days: 71 < 75 = not warmer no more days to check. result: `answer = [1,1,0,0]`
- **6. day 3 temperature = 71** there are no future days to check. result: `answer = [1,1,0,0]`
- **7. loop ends**
days `2` and `3` never find a warmer future temperature.
their answers remain `0`.

 ```
for each day
check every future day
if a warmer temperature is found
record how many days it took
stop searching for that day
if no warmer temperature exists
answer stays 0
```
