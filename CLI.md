# CLI

In late 90's Microsoft has started the development of .Net framework under the name 
of NGWS(Next Generation Window Systems) 

To develop the framework first they have prepared a set of specification for all the .net 
language known as CLI (Common language infrastructure) 

This CLI talks about 4 important things in it: 

* **CLS** (Common Language Specification) 

  It is a set of base rules for all the .net languages to communicate with each other. 

  After compilation of any .net language they must generate the same output code. That 
  is CIL or MSIL code.

  Example: 
  
  VB.Net ----> VBC ----> CIL Code
  
  C#.Net ----> CSC ----> CIL Code

* **CTS** (Common Type System)

  * According to the CTS all the .net Language has to adopt "Uniform Data Types 
Structure", means similar data types must be same in size under the languages of .net. 

  * Now if Wvo .net languages want to communicate with each other then size of data type 
will not be a problem in development. 

  * Interestingly when we compiled any .net language then the data types of the language 
also get converted into a same type that is CIL Code type 

  * So when we want to consume the code of one .net language code from other .net 
language, then the data types of fist language are first converted into CIL type and 
present to the second language as it can be understand by the second language. 

* **BCL** (Base Class Library) 
  It is deveoped in C# and used by other .NET languages
* VSE or **CLR**(VirtuaI Execution System or Common Language Runtime)
