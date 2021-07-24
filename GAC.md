it's a way to keep DLLs globally accessible without worrying about conflicts. No more DLL Hell. Each architecture and version gets it's own place to live.

It also gets it own way to browse it in Explorer, so if you go to

```dos

C:\Windows\assembly

```

In windows explorer it lists all the DLLs.

But if you fire up cmd, you can see how it's really structured:

```dos

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

