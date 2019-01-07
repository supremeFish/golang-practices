
# golang practices on hackerrank

- [Solve Me First](#solve-me-first)
- [Simple Array Sum](#simple-array-sum)

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

## Simple Array Sum
> Given an array of integers, find the sum of its elements.
>
> For example, if the array , , so return .
>
> **Function Description**
>
> Complete the simpleArraySum function in the editor below. It must return the sum of the array elements as an integer.
>
> simpleArraySum has the following parameter(s):
> 
> - ar: an array of integers

> **Input Format**
>
> The first line contains an integer, , denoting the size of the array. 
> The second line contains  space-separated integers representing the array's elements.
>
> **Output Format**
>
> Print the sum of the array's elements as a single integer.

**solution:**
```golang
package main

import (
    "bufio"
    "fmt"
    "io"
    "os"
    "strconv"
    "strings"
)

func simpleArraySum(ar []int32) int32 {
    var sum int32
    for _, v := range ar {
        sum += v
    }
    return sum
}

func main() {
    reader := bufio.NewReaderSize(os.Stdin, 1024 * 1024)

    stdout, err := os.Create(os.Getenv("OUTPUT_PATH"))
    checkError(err)

    defer stdout.Close()

    writer := bufio.NewWriterSize(stdout, 1024 * 1024)

    arCount, err := strconv.ParseInt(readLine(reader), 10, 64)
    checkError(err)

    arTemp := strings.Split(readLine(reader), " ")

    var ar []int32

    for arItr := 0; arItr < int(arCount); arItr++ {
        arItemTemp, err := strconv.ParseInt(arTemp[arItr], 10, 64)
        checkError(err)
        arItem := int32(arItemTemp)
        ar = append(ar, arItem)
    }

    result := simpleArraySum(ar)

    fmt.Fprintf(writer, "%d\n", result)

    writer.Flush()
}

func readLine(reader *bufio.Reader) string {
    str, _, err := reader.ReadLine()
    if err == io.EOF {
        return ""
    }

    return strings.TrimRight(string(str), "\r\n")
}

func checkError(err error) {
    if err != nil {
        panic(err)
    }
}
```
