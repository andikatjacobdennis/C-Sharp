# Comments

## Single-line Comments

```csharp
// This is a comment
Console.WriteLine("Hello World!");
```

## Multi-line Comments

```csharp
/* The code below will print the words Hello World
to the screen, and it is amazing */
Console.WriteLine("Hello World!"); 
```

## XML tags comments

```csharp
/// <summary>
/// Enter description for method someMethod.
/// <see cref="Method(string[])"/>
/// </summary>
/// <param name="str">Describe parameter.</param>
/// <param name="num">Describe parameter.</param>
/// <param name="ptr">Describe parameter.</param>
/// <returns>Describe return value.</returns>
int someMethod(string str, ref int nm, void* ptr) 
{ 
  Method("String1", "String2");
  return 1;
}

public static void Method(params string[] values)
{
    foreach (string value in values)
    {
        Console.WriteLine(value);
    }
}
```

Shortcut: You can use Ctrl+K, Ctrl+C and Ctrl+K, Ctrl+U to Comment or Uncomment selected lines of text.
