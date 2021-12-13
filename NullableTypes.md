# Nullable Types

allow you to assign null to value type variables

Example

```csharp
Nullable<int> i = null;
```

The Nullable types are instances of System.Nullable<T> struct.

```csharp
[Serializable]
public struct Nullable<T> where T : struct
{        
    public bool HasValue { get; }
      
    public T Value { get; }
        
    // other implementation
}
```
    
If we use Value instead of GetValueOrDefault ot will give the following error
    
    
```csharp
static void Main(string[] args)
{
    Nullable<int> i = null;

    Console.WriteLine(i.GetValueOrDefault()); 
} 
```
    
```console
Run-time exception (line 9): Nullable object must have a value.

Stack Trace:

[System.InvalidOperationException: Nullable object must have a value.]
   at System.ThrowHelper.ThrowInvalidOperationException(ExceptionResource resource)
   at System.Nullable`1.get_Value()
   at Program.Main() :line 9
```
    
## Nullable Helper
    
```csharp
static void Main(string[] args)
{
    int? i = null;
    int j = 10;

    if (Nullable.Compare<int>(i, j) < 0)
        Console.WriteLine("i < j");
    else if (Nullable.Compare<int>(i, j) > 0)
        Console.WriteLine("i > j");
    else
        Console.WriteLine("i = j");
} 
```
