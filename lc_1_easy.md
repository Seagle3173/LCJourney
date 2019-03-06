### Given an array of integers, return indices of the two numbers such that they add up to a specific target.
### You may assume that each input would have exactly one solution, and you may not use the same element twice.
### Example:

> 
Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].

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
