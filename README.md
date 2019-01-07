
# golang practices on hackerrank

- [Solve Me First](#solve-me-first)

## Solve Me First

> Complete the function solveMeFirst to compute the sum of two integers.
> 
> Function prototype:
>
> int solveMeFirst(int a, int b);
>
> where,
> - a is thefirst integer input.
> - b is the second integer input.
> 
> Return values
>
> sum of the above two integers

**solution:**

```golang
package main
import "fmt"

func solveMeFirst(a uint32,b uint32) uint32{
    return a + b
}

func main() {
    var a, b, res uint32
    fmt.Scanf("%v\n%v", &a,&b)
    res = solveMeFirst(a,b)
    fmt.Println(res)
}
```
