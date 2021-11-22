# Type

## Default constructors

All value types implicitly declare a public parameterless instance constructor called the ***default constructor***. The default constructor returns a zero-initialized instance known as the ***default value*** for the value type:

*  For all *simple_type*s, the default value is the value produced by a bit pattern of all zeros:
    * For `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, and `ulong`, the default value is `0`.
    * For `char`, the default value is `'\x0000'`.
    * For `float`, the default value is `0.0f`.
    * For `double`, the default value is `0.0d`.
    * For `decimal`, the default value is `0.0m`.
    * For `bool`, the default value is `false`.
*  For an *enum_type* `E`, the default value is `0`, converted to the type `E`.
*  For a *struct_type*, the default value is the value produced by setting all value type fields to their default value and all reference type fields to `null`.
*  For a *nullable_type* the default value is an instance for which the `HasValue` property is false and the `Value` property is undefined. The default value is also known as the ***null value*** of the nullable type.

## Integral types

C# supports nine integral types: `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, and `char`. The integral types have the following sizes and ranges of values:

*  The `sbyte` type represents signed 8-bit integers with values between -128 and 127.
*  The `byte` type represents unsigned 8-bit integers with values between 0 and 255.
*  The `short` type represents signed 16-bit integers with values between -32768 and 32767.
*  The `ushort` type represents unsigned 16-bit integers with values between 0 and 65535.
*  The `int` type represents signed 32-bit integers with values between -2147483648 and 2147483647.
*  The `uint` type represents unsigned 32-bit integers with values between 0 and 4294967295.
*  The `long` type represents signed 64-bit integers with values between -9223372036854775808 and 9223372036854775807.
*  The `ulong` type represents unsigned 64-bit integers with values between 0 and 18446744073709551615.
*  The `char` type represents unsigned 16-bit integers with values between 0 and 65535. The set of possible values for the `char` type corresponds to the Unicode character set. Although `char` has the same representation as `ushort`, not all operations permitted on one type are permitted on the other.
