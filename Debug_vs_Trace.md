# Debug vs	Trace

 Debug                                               | Trace           
:----------------------------------------------------|:-------------
It uses the Debug class.                             | It uses the Trace class.
It uses the time of application development.         | It uses the time of application deployment.    
It works only in debug mode.                         | It works in both case debug and release mode.     
It can be used Debug.Write() method for debug.       | It can be used to Trace.Write() method for trace.
It runs in the same thread as main program executes. | It runs in different thread form main program execute thread.
It is used to find errors in the program.            | It is used for testing and optimization even after an application is compiled and released.
