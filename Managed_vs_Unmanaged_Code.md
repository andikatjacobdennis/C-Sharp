# Managed vs Unmanaged Code

* Managed code executed by CLR. Unmanaged code executed by OS
* CLR provides various services like type checking, garbage collection, exception Handling. OS do not provide those services.
* The code is compiled by language compiler to IL code. In unmanaged code compiled directly into native code. 
* Contrast this to the way you would run a C/C++ program, also called "unmanaged code". In the unmanaged world, the programmer is in charge of pretty much everything. The actual program is, essentially, a binary that the operating system (OS) loads into memory and starts. Everything else, from memory management to security considerations are a burden of the programmer.
* C# is one language that allows you to use unmanaged constructs such as pointers directly in code by utilizing what is known as unsafe context which designates a piece of code for which the execution is not managed by the CLR.
