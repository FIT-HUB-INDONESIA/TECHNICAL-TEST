# The Assignment

Refactor this inventory management system to address several issues:
- Eliminate the use of global state for inventory, which can lead to unintended side effects, testing difficulties, and potential race conditions in a concurrent setting.
- Design a struct or interface that encapsulates the inventory management logic.
- Ensure that the refactored code is safe for concurrent access.
- Maintain the ability to perform operations like adding to inventory, removing from inventory, and querying the current inventory.

## The Code

```go

package main

import (
	"fmt"
	"sync"
)

var inventory map[string]int
var mu sync.Mutex

func init() {
	inventory = make(map[string]int)
}

func addToInventory(item string, quantity int) {
	mu.Lock()
	defer mu.Unlock()

	inventory[item] += quantity
}

func removeFromInventory(item string, quantity int) {
	mu.Lock()
	defer mu.Unlock()

	if currentQuantity, ok := inventory[item]; ok {
		if currentQuantity >= quantity {
			inventory[item] -= quantity
		} else {
			fmt.Println("Error: Insufficient quantity in inventory.")
		}
	} else {
		fmt.Println("Error: Item not found in inventory.")
	}
}

func getInventory() map[string]int {
	mu.Lock()
	defer mu.Unlock()

	return inventory
}

func main() {

	// Simulate inventory transactions
	addToInventory("Laptop", 5)
	removeFromInventory("Laptop", 2)
	removeFromInventory("Desktop", 3)

	// Print current inventory
	fmt.Println("Current Inventory:", getInventory())
}

```
