# Bin and Obj folders

When you compile C# programs, you would see 2 folders “bin” and “obj”. In this article, we will try to understand the difference and importance of these folders.

Both these folders have compiled IL code, but the question is why not just one folder and why two folders?

![Image 1][Resources/bin_and_obj/bin_and_obj_1.jpg]
We have two folders because the compilation process goes through two steps, compiling and linking. See the below diagram.

In compiling phase, every code file is compiled into individual compiled units. So if you have two code files, two independent compiled codes will be generated.
In linking phase, all these compiled code files are linked and compiled into a single unit assembly which can be a DLL or EXE.
Image 2
If you compare both the folders (see the below image), you will find more files in “obj” folder as compared to “bin” folder. We have more files in “obj” folder because it creates separate compiled code files for each source code file.

Image 3
So the next question which comes to our mind is why do we need compiling in two phases, why not just do it in one go. By doing the two phase compiling, we achieve incremental or conditional compiling.

When we work with big projects, we will have a lot of code files and we would like to only compile those code files which have changed. In the “obj” folder we have entry of each code file compilation. So we can know from the same which files exactly have changed, thus making compiling fast.

Image 4
In summary, in “obj” folder, we have compiled files for each source code file and in “bin” folder, we have a single unit which links all individually compiled code files.

Below is a 10 minute YouTube video which demonstrates how both these folders look like and how incremental compilation happens.

[![C# bin vs obj folder](bin_and_obj_4.jpg)](https://www.youtube.com/watch?v=vjHage_2g4Y)
