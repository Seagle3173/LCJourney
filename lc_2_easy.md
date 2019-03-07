### Given a 32-bit signed integer, reverse digits of an integer.
### Example 1:

> Input: 123
> Output: 321

### My Anwser:
```go
func reverse(x int) int {
    y := 0
    for x!=0{
        pop:=x%10
        x=x/10
        y=y*10+pop
        if y>((1<<31)-1) || y<(-(1<<31)){
            return 0
        }
    }
    return y
}
```
| Runtime | Memory |
| ------ | ------ |
| 4ms | 2.2MB |
| 100% | 100% |

#### Fine!
