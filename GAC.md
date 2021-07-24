# Global Assembly Cache


It's a way to keep DLLs globally accessible without worrying about conflicts. No more DLL Hell. Each architecture and version gets it's own place to live.

It also gets it own way to browse it in Explorer, so if you go to

```cmd

C:\Windows\assembly

```

In windows explorer it lists all the DLLs.

But if you fire up cmd, you can see how it's really structured:

```cmd

C:\Windows\assembly>dir

 Directory of C:\Windows\assembly

07/20/2009  02:18 PM    <DIR>          GAC
06/17/2009  04:22 PM    <DIR>          GAC_32
06/17/2009  04:22 PM    <DIR>          GAC_64
06/17/2009  04:22 PM    <DIR>          GAC_MSIL
 ...snip...
               0 File(s)              0 bytes
               9 Dir(s)  90,538,311,680 bytes free

C:\Windows\assembly>cd GAC_64

C:\Windows\assembly\GAC_64>dir

 Directory of C:\Windows\assembly\GAC_64

06/17/2009  04:22 PM    <DIR>          .
06/17/2009  04:22 PM    <DIR>          ..
01/19/2008  09:54 AM    <DIR>          blbproxy
 ...snip...
01/19/2008  09:54 AM    <DIR>          srmlib
01/19/2008  06:11 AM    <DIR>          System.Data
01/19/2008  06:11 AM    <DIR>          System.Data.OracleClient
 ...snip...
               0 File(s)              0 bytes
              34 Dir(s)  90,538,311,680 bytes free

C:\Windows\assembly\GAC_64>cd System.Data

C:\Windows\assembly\GAC_64\System.Data>dir
 Directory of C:\Windows\assembly\GAC_64\System.Data

01/19/2008  06:11 AM    <DIR>          .
01/19/2008  06:11 AM    <DIR>          ..
04/11/2009  12:20 PM    <DIR>          2.0.0.0__b77a5c561934e089
               0 File(s)              0 bytes
               3 Dir(s)  90,538,311,680 bytes free

C:\Windows\assembly\GAC_64\System.Data>cd 2.0.0.0__b77a5c561934e089

C:\Windows\assembly\GAC_64\System.Data\2.0.0.0__b77a5c561934e089>dir

 Directory of C:\Windows\assembly\GAC_64\System.Data\2.0.0.0__b77a5c561934e089

04/11/2009  12:20 PM    <DIR>          .
04/11/2009  12:20 PM    <DIR>          ..
04/11/2009  12:12 PM         3,008,512 System.Data.dll
               1 File(s)      3,008,512 bytes
               2 Dir(s)  90,538,311,680 bytes free

C:\Windows\assembly\GAC_64\System.Data\2.0.0.0__b77a5c561934e089>
              
```

Here you can see version 2.0.0.0__b77a5c561934e089 of System.Data.

A DLL is identified by 5 parts:

* Name
* Version
* Architecture
* Culture
* Public Key

Although the first 3 are generally the big ones.

Exe Application, first of all, references from a current directory to a subdirectory. And then, system directory. VS6.0 system directory was ..windows/system32. .NET system directory is like the below GAC path.

GAC path

1) C:\Windows\Assembly (for .NET 2.0 ~ 3.5)

2) C:\Windows\Microsoft.NET\assembly (for .NET 4.0)

## How to install an assembly into GAC (as Administrator)

1) Drag and Drop

2) Use GacUtil.exe with Visual Studio Command Prompt

```cmd

 gacutil -i [Path][Assembly Name].dll

```

Note: To install an assembly into the GAC, the assembly must be strongly named. Otherwise you get an error like this: Failure adding assembly to the cache: Attempt to install an assembly without a strong name.
How to uninstall an assembly from GAC (as Administrator)

```cmd

 gacutil -u [Assembly Name], Version=1.0.0.0, PublickeyToken=7896a3567gh

```

Note: has no extention, .dll. Version and PublickeyToken can be omitted and be checked in GAC assembly.

## Create and sign an assembly with a strong name by using the Assembly Linker

Open Visual Studio Developer Command Prompt or Visual Studio Developer PowerShell, and enter the following command:

al /out:<assemblyName> <moduleName> /keyfile:<keyfileName>

Where:

assemblyName is the name of the strongly signed assembly (a .dll or .exe file) that Assembly Linker will emit.

moduleName is the name of a .NET Framework code module (a .netmodule file) that includes one or more types. You can create a .netmodule file by compiling your code with the /target:module switch in C# or Visual Basic.

keyfileName is the name of the container or file that contains the key pair. Assembly Linker interprets a relative path in relation to the current directory.

The following example signs the assembly MyAssembly.dll with a strong name by using the key file sgKey.snk.

```cmd

Copy
al /out:MyAssembly.dll MyModule.netmodule /keyfile:sgKey.snk  

```
