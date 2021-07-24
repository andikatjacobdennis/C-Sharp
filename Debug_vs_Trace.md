# Debug vs	Trace

- Debug

It is used to debug your code in development environment only.
Debugging is the process of finding and fixing errors in your code.
It works when solution configuration mode is Debug. In Release mode it does not write anything on the output window.
In debugging there is no such facility to differentiate between message types (Information, Error, Warning).

Example

```csharp

Debug.WriteLine("Debug Start");
Debug.Indent();            
Debug.WriteLine("Main Start");          
Debug.WriteLine("Main End");
Debug.Unindent();
Debug.WriteLine("Debug End");
Debug.Flush();
Debug.Close();

```

- Trace

It is used to trace the execution of your code in development as well as production environment.
Tracing is the process of collecting information about the program’s execution.
It works in both solution configuration modes Debug and Release.
In tracing we can easily differentiate between message types (Information, Error, Warning) using  Trace.TraceInformation, Trace.TraceError and Trace.TraceWarning.

Example

```csharp

Trace.WriteLine("Trace Start");         
Trace.Indent();
Trace.TraceInformation("Information");
Trace.TraceError("Error");
Trace.TraceWarning("Warning");
Trace.WriteLine("Main Start");
Trace.WriteLine("Main End");
Trace.Unindent();
Trace.WriteLine("Trace End");
Trace.Flush();
Trace.Close();

```
