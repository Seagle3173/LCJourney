### Given an array of integers, return indices of the two numbers such that they add up to a specific target.
### You may assume that each input would have exactly one solution, and you may not use the same element twice.
### Example:

> 
Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].


My First Answer:
```go
func twoSum(nums []int, target int) []int {
    var res []int
    ALoop:
    for i:=0;i<len(nums)-1;i++{
        for j:=i+1;j<len(nums);j++{
            if nums[i]+nums[j]==target{
                res=append(res,i,j)
                break ALoop
            }
        }
    }
    return res
}
```

### Tooooooo Slow


| Runtime | Memory |
| ------ | ------ |
| 36ms | 2.9MB |
| ------ | ------ |
| 40.67% | 86.76% |

My Second Anwser:
```go
func twoSum(nums []int, target int) []int {
    var res []int
    var myMap map[int] int
    myMap=make(map[int] int)
    for i,value:=range(nums){
        myMap[value]=i
    }
    for i,value:=range(nums){
        j,ok:=myMap[target-value]
        if ok&&i!=j{
            res=append(res,i,j)
            break
        }
    }
    return res
}
```
| Runtime | Memory |
| ------ | ------ |
| 4ms | 3.8MB |
| ------ | ------ |
| 100% | 15.95% |
