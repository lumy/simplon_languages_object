
# C# (csharp)

https://www.w3schools.com/cs/cs_getstarted.php
https://docs.microsoft.com/en-us/dotnet/csharp/
https://docs.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/
https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/language-specification/introduction
https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/


## Environment

C# can run and be compiled pretty easily under windows.
It can run and compile with mono under linux.
It rely on .NET (framework) libraries.

## Entrypoint

By convention, a static method named Main serves as the entry point of a program.

```c#
using System;

class Hello
{
    static void Main() {
        Console.WriteLine("Hello, World");
    }
}
```

## Type

Unlike python, C# implement the `Interface`, `const` paradigm, the
And a lot of others (pretty common, array, int, str....)

## Switch

Unlike python, C# implement the switch operator:

```java
string y = "toto";
switch(expression) {
  case "my-sentences":
    // code block
    break;
  case y:
    // code block
    break;
  default:
    // code block
}
```

`break` is really important !

## Operator

like Python you can do `i += 1` but you can do `i++` or `i = i + 1` (same for `-=` and `--`)
