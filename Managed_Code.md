# Managed Code

Code that you develop with a language compiler that targets the runtime is called managed code. 

Managed code benefits from features such as 

* **cross-language integration**
* **cross-language exception handling**
* enhanced **security**
* **debugging** and **profiling** services.
* **versioning** and **deployment** support

Contrast this to the way you would run a C/C++ program, also called "unmanaged code". In the unmanaged world, the programmer is in charge of pretty much everything. The actual program is, essentially, a binary that the operating system (OS) loads into memory and starts. Everything else, from memory management to security considerations are a burden of the programmer.

C# is one language that allows you to use unmanaged constructs such as pointers directly in code by utilizing what is known as unsafe context which designates a piece of code for which the execution is not managed by the CLR.
