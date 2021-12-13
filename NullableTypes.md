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
