# The Assignment
Please review this Golang snippet.

```go
package main

import "fmt"

// Calculator struct represents a simple calculator.
type Calculator struct {
	result int
}

// Add adds two numbers and sets the result.
func (c *Calculator) Add(a, b int) {
	c.result = a + b
}

// Subtract subtracts one number from another and sets the result.
func (c *Calculator) Subtract(a, b int) {
	c.result = a - b
}

// Multiply multiplies two numbers and sets the result.
func (c *Calculator) Multiply(a, b int) {
	c.result = a * b
}

// Divide divides one number by another and sets the result.
func (c *Calculator) Divide(a, b int) {
	if b != 0 {
		c.result = a / b
	} else {
		fmt.Println("Error: Cannot divide by zero.")
	}
}

// PrintResult prints the current result.
func (c *Calculator) PrintResult() {
	fmt.Println("Result:", c.result)
}

func main() {
	calculator := Calculator{}

	calculator.Add(5, 3)
	calculator.PrintResult()

	calculator.Subtract(10, 4)
	calculator.PrintResult()

	calculator.Multiply(3, 7)
	calculator.PrintResult()

	calculator.Divide(8, 2)
	calculator.PrintResult()

	calculator.Divide(6, 0)
	calculator.PrintResult()
}
```
