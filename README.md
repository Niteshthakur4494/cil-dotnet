### IL(Intermediate Language)

> The Common Intermediate Language (CIL) is a low-level programming language used in the .Net framework. It is an intermediate language that all .NET languages compile to before being executed by the NET runtime.
> CIL provides a level of abstraction that allows for language interoperability, enabling code written in different .NET languages(such as C#, VB.NET, and F#) to work seamlessly.


### Getting Started

#### Clone this repo to local development
```
git clone https://github.com/Niteshthakur4494/cil-dotnet.git
```

### Consider a simple C# program in VS 2019/2022
```
using System;

namespace cil_example
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

### To view the IL code we have to use [ildasm](https://learn.microsoft.com/en-us/dotnet/framework/tools/ildasm-exe-il-disassembler) tool from Microsoft 

The IL Disassembler is a companion tool to the IL Assembler (Ilasm.exe). Ildasm.exe takes a portable executable (PE) file that contains intermediate language (IL) code and creates a text file suitable as input to Ilasm.exe.

This tool is automatically installed with Visual Studio. To run the tool, use Visual Studio Developer Command Prompt or Visual Studio Developer PowerShell

### Build repo and open exe file in (Ildasm)

Next, we need to open the output file in Ildasm to examine the CIL code. Launch the Ildasm tool by following the above section. Click on File->Open and select an output file like cil-example.exe

You can also drag and drop files onto the instance of Ildasm.

You can see below the UI contains CLI, manifest section
Ildasm Tool: 

![alt text][ildasmTool]

CIL Code:

![alt text][cilCode]

[ildasmTool]: /images/ildasmTool.jpg "Ildasm Tool"
[cilCode]: /images/cli-example.jpg "cil-code"


In this CIL code:

* `.method` declares the `Main` method.
* `.entrypoint` indicates that this is the entry point of the program.
* `ldstr "Hello, World!"` loads the string "Hello, World!" onto the evaluation stack.
* `call void [mscorlib]System.Console::WriteLine(string)` calls the `WriteLine` method of the `System.Console` class to print the string to the console.
* `ret` returns from the method.

Understanding CIL can provide deeper insights into how .NET applications are executed and optimized
