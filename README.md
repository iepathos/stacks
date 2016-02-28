
# Example using stacks library

````go
package main

import (
    "fmt"
    "github.com/iepathos/stacks"
)

func main() {
    strStack := new(stacks.Stack)

    strStack.Push("Things")
    strStack.Push("and")
    strStack.Push("Stuff")

    for strStack.Len() > 0 {
        // We have to do a type assertion because we get back a variable of type
        // interface{} while the underlying type is a string.
        fmt.Printf("%s ", strStack.Pop().(string))
    }
    fmt.Println()

    intStack := new(stacks.Stack)

    intStack.Push(1)
    intStack.Push(5)
    intStack.Push(12)

    for intStack.Len() > 0 {
        // We have to do a type assertion because we get back a variable of type
        // interface{} while the underlying type is a int.
        fmt.Printf("%v ", intStack.Pop().(int))
    }
    fmt.Println()
}
````