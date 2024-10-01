### Kotlin Cheat Sheet

#### 1. Basic Syntax

```kotlin
fun main() {
    println("Hello, Kotlin!")
}
```

- **fun**: Declares a function.
- **println**: Prints to the console.

#### 2. Variables

```kotlin
val immutable = 42   // read-only variable (like `final` in Java)
var mutable = 43     // mutable variable
```

- **val**: Immutable variable (cannot be reassigned).
- **var**: Mutable variable (can be reassigned).

#### 3. Data Types

Kotlin has the following basic data types:

- **Int**: 32-bit integer.
- **Long**: 64-bit integer.
- **Float**: 32-bit floating-point number.
- **Double**: 64-bit floating-point number.
- **Boolean**: Represents `true` or `false`.
- **String**: Represents a sequence of characters.

```kotlin
val intNum: Int = 10
val longNum: Long = 100L
val floatNum: Float = 10.5F
val doubleNum: Double = 20.99
val isKotlinFun: Boolean = true
val name: String = "Kotlin"
```

#### 4. String Interpolation

```kotlin
val name = "Kotlin"
println("Hello, $name!")
println("2 + 2 is ${2 + 2}")
```

- Use `$` to insert variables into strings.
- Use `${}` for expressions inside strings.

#### 5. Conditionals

```kotlin
val a = 10
val b = 20
val max = if (a > b) a else b
```

- **if-else**: Can be used as an expression returning a value.
  
```kotlin
val grade = 85
val result = when (grade) {
    in 90..100 -> "A"
    in 80..89 -> "B"
    in 70..79 -> "C"
    else -> "F"
}
```

- **when**: Kotlin’s version of switch-case.

#### 6. Loops

```kotlin
for (i in 1..5) {
    println(i)  // prints numbers from 1 to 5
}
```

- **for**: Iterate over a range.
  
```kotlin
var x = 0
while (x < 5) {
    println(x)
    x++
}
```

- **while**: Repeat a block while the condition is true.

```kotlin
var y = 0
do {
    println(y)
    y++
} while (y < 5)
```

- **do-while**: Similar to while, but checks condition after the first loop.

#### 7. Functions

```kotlin
fun add(a: Int, b: Int): Int {
    return a + b
}
```

- **fun**: Declares a function, return type follows the arguments.

```kotlin
fun subtract(a: Int, b: Int) = a - b
```

- Single-expression functions can omit the `return` keyword.

#### 8. Nullable Types

```kotlin
var nullableString: String? = null
```

- `?` after the type indicates that it can hold `null`.

```kotlin
nullableString?.length  // Safe call: returns length if non-null, else null.
nullableString!!.length // Force call: throws NullPointerException if null.
```

#### 9. Elvis Operator

```kotlin
val len = nullableString?.length ?: 0
```

- **?:** The Elvis operator returns the value on the left if it's not null, otherwise returns the value on the right.

#### 10. Classes and Objects

```kotlin
class Person(val name: String, var age: Int)
```

- **class**: Defines a class.
- The constructor is declared directly in the class header.

```kotlin
val person = Person("Alice", 25)
println(person.name)
person.age = 26
```

#### 11. Inheritance

```kotlin
open class Animal {
    open fun makeSound() {
        println("Some sound")
    }
}

class Dog : Animal() {
    override fun makeSound() {
        println("Bark")
    }
}
```

- **open**: Allows the class/method to be overridden.
- **override**: Overrides a method.

#### 12. Data Classes

```kotlin
data class User(val name: String, val age: Int)
```

- **data class**: Provides automatic `equals()`, `hashCode()`, `toString()`, and `copy()` functions.

```kotlin
val user = User("John", 30)
println(user)           // User(name=John, age=30)
val copyUser = user.copy(age = 35)
```

#### 13. Lambda Functions

```kotlin
val sum = { a: Int, b: Int -> a + b }
println(sum(10, 20))   // Output: 30
```

- **{ parameters -> body }**: Lambda expression syntax.

#### 14. Higher-Order Functions

```kotlin
fun applyOperation(x: Int, y: Int, operation: (Int, Int) -> Int): Int {
    return operation(x, y)
}
println(applyOperation(3, 4, sum))  // Output: 7
```

- Functions that take other functions as parameters or return them.

#### 15. Collections

```kotlin
val numbers = listOf(1, 2, 3)
val mutableNumbers = mutableListOf(1, 2, 3)
mutableNumbers.add(4)
```

- **listOf**: Immutable list.
- **mutableListOf**: Mutable list.

```kotlin
val set = setOf(1, 2, 3)
val mutableSet = mutableSetOf(1, 2, 3)
```

- **setOf**: Immutable set (unique elements).

```kotlin
val map = mapOf("a" to 1, "b" to 2)
val mutableMap = mutableMapOf("a" to 1, "b" to 2)
```

- **mapOf**: Immutable map (key-value pairs).

#### 16. Extension Functions

```kotlin
fun String.greet() {
    println("Hello, $this!")
}
"World".greet()   // Output: Hello, World!
```

- Adds new functionality to existing classes without modifying them.

#### 17. Sealed Classes

```kotlin
sealed class Result
class Success(val message: String) : Result()
class Failure(val error: String) : Result()
```

- **sealed**: Restricts class inheritance to specific types within the same file.

#### 18. Coroutines (Basic)

```kotlin
import kotlinx.coroutines.*

fun main() = runBlocking {
    launch {
        delay(1000L)
        println("World!")
    }
    println("Hello,")
}
```

- **launch**: Starts a new coroutine.
- **runBlocking**: Blocks the current thread until the coroutine inside finishes.
- **delay**: Suspends coroutine without blocking the thread.

#### 19. Exceptions

```kotlin
try {
    val result = riskyOperation()
} catch (e: Exception) {
    println("Error: ${e.message}")
} finally {
    println("Cleanup")
}
```

- **try-catch**: Handles exceptions.
- **finally**: Optional block that always executes.

#### 20. Generics

```kotlin
fun <T> genericFunc(item: T): T {
    return item
}
```

- **< T >**: Declares a generic type.

---
