# The Assignment
Please review this Golang snippet.

```go
package main

import "fmt"

func main() {
	// Create a slice of numbers.
	numbers := []int{1, 2, 3, 4, 5}

	// Print the sum of the numbers.
	sum := sumNumbers(numbers)
	fmt.Println("Sum of numbers:", sum)

	// Print the average of the numbers.
	average := averageNumbers(numbers)
	fmt.Println("Average of numbers:", average)
}

func sumNumbers(nums []int) int {
	// Calculate the sum of the numbers.
	sum := 0
	for i := 0; i < len(nums); i++ {
		sum += nums[i]
	}
	return sum
}

func averageNumbers(nums []int) float64 {
	// Calculate the average of the numbers.
	sum := sumNumbers(nums)
	average := float64(sum) / float64(len(nums))
	return average
}
```
