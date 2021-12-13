# Enum

An enumeration type (or enum type) is a value type defined by a set of named constants of the underlying integral numeric type. 

```csharp
enum ErrorCode : ushort
{
    None = 0,
    Unknown = 1,
    ConnectionLost = 100,
    OutlierReading = 200
}
```
