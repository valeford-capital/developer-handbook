# Valeford Capital Coding Style Guide for Swift

## Purpose
This guide defines the coding standards for all Swift projects at Valeford Capital. Our goal is to maintain a **simple, clean, and consistent codebase** that is easy to read, maintain, and scale.

---

## General Guidelines
1. **Clarity is key**: Write code that is easy to read and understand.
2. **Consistency over personal preference**: Follow this guide, even if it differs from your individual style.
3. **Use descriptive names**: Variables, functions, and classes should clearly convey their purpose.
4. **Avoid unnecessary complexity**: Favor straightforward solutions over clever but obscure implementations.

---

## Naming Conventions

### Variables and Constants
- Use `camelCase` for variable and function names.
- Use `UPPER_CASE_SNAKE_CASE` for constants.

Examples:
```swift
var userName: String
let MAX_USERS: Int = 100
```

### Classes, Structs, Enums, and Protocols
- Use `PascalCase`.

Examples:
```swift
class UserProfile {}
struct UserSettings {}
enum UserType {}
protocol UserDelegate {}
```

### Functions and Methods
- Use `camelCase`.
- Function names should describe their purpose.

Examples:
```swift
func calculateTotalPrice() -> Double {}
func fetchUserData(for userID: String) {}
```

### File Names
- Use `PascalCase` and match the main type in the file.

Examples:
- `UserProfile.swift`
- `SettingsView.swift`

---

## Formatting Rules

### Indentation and Spacing
- **Use 4 spaces** for indentation.
- **No tabs**.

### Line Length
- Keep lines to a maximum of **100 characters**.

### Braces
- Open braces `{` go on the **same line** as the statement.
- Closing braces `}` align with the opening statement.

Examples:
```swift
if isValid {
    print("Valid")
} else {
    print("Invalid")
}
```

### Blank Lines
- Use blank lines to separate logical sections of code.
- No more than one consecutive blank line.

### Function Layout
- Leave one blank line before and after each function.

Example:
```swift
func calculateDiscount() -> Double {
    // Function logic
}

func fetchData() {
    // Function logic
}
```

---

## Commenting Guidelines

### Single-Line Comments
- Use `//` for brief explanations.

Example:
```swift
// Calculate the total price of items
let totalPrice = items.reduce(0, +)
```

### Multi-Line Comments
- Use `/* */` for longer explanations.

Example:
```swift
/*
 This function fetches user data from the API.
 It retries up to 3 times in case of failure.
*/
func fetchUserData() {}
```

### Documenting Functions
- Use Swift’s built-in documentation syntax (`///`) for public or complex functions.

Example:
```swift
/// Calculates the total price of all items in the cart.
/// - Returns: The total price as a Double.
func calculateTotalPrice() -> Double {}
```

---

## Code Organization

### File Structure
- Group related files into folders:
  - **Models**: For structs and classes representing data.
  - **Views**: For SwiftUI views.
  - **Controllers**: For business logic.
  - **Utilities**: For helper functions and extensions.

### Order Within a File
1. Imports
2. Constants and Enums
3. Properties
4. Initializers
5. Methods (public before private)

Example:
```swift
import SwiftUI

struct UserProfile {
    // Properties
    var name: String
    var age: Int

    // Initializers
    init(name: String, age: Int) {
        self.name = name
        self.age = age
    }

    // Methods
    func displayInfo() {
        print("\(name), \(age) years old")
    }
}
```

---

## Best Practices

### Error Handling
- Use `guard` statements for early exits.

Example:
```swift
func processOrder(order: Order?) {
    guard let order = order else {
        print("Invalid order")
        return
    }
    // Process the order
}
```

### Optionals
- Always safely unwrap optionals using `if let` or `guard`.

Example:
```swift
if let user = user {
    print(user.name)
} else {
    print("No user found")
}
```

### Avoid Magic Numbers
- Use named constants instead of hardcoding numbers or strings.

Example:
```swift
let maxRetries = 3
for _ in 0..<maxRetries {
    // Retry logic
}
```

### Extensions
- Use extensions to group related functionality.

Example:
```swift
extension String {
    func isValidEmail() -> Bool {
        // Validation logic
        return true
    }
}
```

---

## Tools
- **SwiftLint**: Use SwiftLint to enforce these coding standards automatically.
- **Xcode Formatting**: Set up Xcode to auto-indent and format code according to this guide.

---

## Updating the Style Guide
This guide should evolve as our team grows and adopts new best practices. Submit proposed updates for review before implementing them.

