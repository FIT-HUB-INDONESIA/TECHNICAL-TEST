# The Assignment
Please review this Golang snippet.

```go
package main

import (
	"fmt"
	"math"
)

// Circle struct represents a circle with a radius.
type Circle struct {
	Radius float64
}

// Area calculates the area of the circle.
func (c Circle) area() float64 {
	return math.Pi * c.Radius * c.Radius
}

func main() {
	// Initialize a circle with a radius of 5.
	var c1 Circle
	c1.Radius = 5

	// Print the area of the circle.
	fmt.Println("Area of the circle:", c1.area())

	// Attempt to change the radius of the circle.
	updateRadius(&c1)

	// Print the area again after updating the radius.
	fmt.Println("Updated area of the circle:", c1.area())
}

// updateRadius updates the radius of the circle to 10.
func updateRadius(c *Circle) {
	c.Radius = 10
}
```
