## Strings
In Kotlin, strings are character arrays. That means elements of a string can be accessed by the indexing operation.
```kotlin
val s = "lovely"
println(s[0]) // prints "l"
println(s[2]) // prints "v"
println(s[4]) // prints "l"
```
We can also use a for-loop to iterate over the string.
```kotlin
for (c in s) {
    print("$c ") // string concatenation using string template.
}
// prints l o v e l y
```

## String Literals
There are two kinds of string available in Kotlin - one is called **escaped strings** and the other is called **raw strings**.
### Escaped Strings
Escaped strings may or may not have escaped characters in them. We can simply think an escaped string as a Java string.
```kotlin
val es = "Hello World!\n"
print(es) // prints "Hello World!"
```
### Raw Strings
Raw strings can contain newlines and arbitrary text. A raw string is delimited by a triple quote(`"""`). Raw strings cannot have escaped characters in them.
```kotlin
val rs = """
    Hello, nice to meet you.
    My name is Junyoung Kim.
    """
val rsWithEscapedChars = """
    Hello, nice to meet you.
    My name is Junyoung Kim.\n\n\n
    """
println(rs)
println(rsWithEscapedChars)
```
Therefore, there is no difference between these two strings. Both println() functions print:
```
        Hello, nice to meet you.
        My name is Junyoung Kim.
```
We can remove leading whitespace with [trimMargin()](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.text/trim-margin.html) function:
```kotlin
val rsNoLeadingWhitespace = """
    |Hello, nice to meet you.
    |My name is Junyoung Kim.
    """.trimMargin()
println(rsNoLeadingWhitespace)
```
The println() function prints:
```
Hello, nice to meet you.
My name is Junyoung Kim.
```
By default `|` is used as margin prefix, but you can choose another character and pass it as a parameter, like
`
trimMargin("#")
`.