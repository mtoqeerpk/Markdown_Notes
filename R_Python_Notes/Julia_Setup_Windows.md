# Julia setup for windows

For windows Please the following

[How to Setup Julia Path to Environment Variable?](https://www.geeksforgeeks.org/how-to-setup-julia-path-to-environment-variable/)

First I need to locate where julia is installed. It was installed at 

`C:\Users\Toqeer\AppData\Local\Programs\Julia\Julia-1.4.2\bin`

**Step 1.** By reading the installation guide I go to 

`Control Panel ---> System and  ---> Security\System`



**Step2.** Then click on the `Advance system settings`

![image-20200624161043232](C:\Users\Toqeer\AppData\Roaming\Typora\typora-user-images\image-20200624161043232.png)

**Step 3.** Then click on the `Environment Variable`

![image-20200624161309660](C:\Users\Toqeer\AppData\Roaming\Typora\typora-user-images\image-20200624161309660.png)



**Step 4.** Then click on `Path`

![image-20200624161544794](C:\Users\Toqeer\AppData\Roaming\Typora\typora-user-images\image-20200624161544794.png)



It will open new wind. On that click on new and add the Julia path which is 

`C:\Users\Toqeer\AppData\Local\Programs\Julia\Julia-1.4.2\bin`



<img src="C:\Users\Toqeer\AppData\Roaming\Typora\typora-user-images\image-20200624161743276.png" alt="image-20200624161743276"  />

Click `ok`

The path has been added

![image-20200624161944395](C:\Users\Toqeer\AppData\Roaming\Typora\typora-user-images\image-20200624161944395.png)

Then I started the Julia and typed

`using Pkg`

then 

`Pkg.add("PyCall")`

![image-20200624162436828](C:\Users\Toqeer\AppData\Roaming\Typora\typora-user-images\image-20200624162436828.png)

```

julia> Pkg.add("PyCall")
    Cloning default registries into `C:\Users\Toqeer\.julia`
    Cloning registry from "https://github.com/JuliaRegistries/General.git"
      Added registry `General` to `C:\Users\Toqeer\.julia\registries\General`
  Resolving package versions...
  Installed VersionParsing ─ v1.2.0
  Installed MacroTools ───── v0.5.5
  Installed Parsers ──────── v1.0.5
  Installed Conda ────────── v1.4.1
  Installed PyCall ───────── v1.91.4
  Installed JSON ─────────── v0.21.0
   Updating `C:\Users\Toqeer\.julia\environments\v1.4\Project.toml`
  [438e738f] + PyCall v1.91.4
   Updating `C:\Users\Toqeer\.julia\environments\v1.4\Manifest.toml`
  [8f4d0f93] + Conda v1.4.1
  [682c06a0] + JSON v0.21.0
  [1914dd2f] + MacroTools v0.5.5
  [69de0a69] + Parsers v1.0.5
  [438e738f] + PyCall v1.91.4
  [81def892] + VersionParsing v1.2.0
  [2a0f44e3] + Base64
  [ade2ca70] + Dates
  [8ba89e20] + Distributed
  [b77e0a4c] + InteractiveUtils
  [8f399da3] + Libdl
  [37e2e46d] + LinearAlgebra
  [56ddb016] + Logging
  [d6f4376e] + Markdown
  [a63ad114] + Mmap
  [de0858da] + Printf
  [9a3f8284] + Random
  [9e88b42a] + Serialization
  [6462fe0b] + Sockets
  [8dfed614] + Test
  [4ec0a83e] + Unicode
   Building Conda ─→ `C:\Users\Toqeer\.julia\packages\Conda\3rPhK\deps\build.log`
   Building PyCall → `C:\Users\Toqeer\.julia\packages\PyCall\zqDXB\deps\build.log`
```
## Adding a package
To install a package use 
`]add DSP` Where DSP is package name. After installation to exit please press
`CTRL+C`

## Using notebook

To launch the IJulia notebook in your browser.

```
using IJulia
notebook()
```

## Running Julia

There are several ways to run Julia code:

1. Julia can be run interactively in a console.

   Once you have it installed, just type `julia` in a console and then enter your commands in the prompt that follows. You can type `exit()` when you have finished;

2. Alternatively, Julia can be written as a script.

   A Julia script is a text file ending in `.jl`, which you can have Julia parse and run with `julia myscript.jl [arg1, arg2,..]`. Script files can also be run from within the Julia console, just type `include("myscript.jl")`;

3. In addition, on UNIX-based systems Julia can be run using a shebang script.

   To make a shebang script, just add the location of the Julia interpreter on your system, preceded by `#!` and followed by an empty row, to the top of the script. You can find the full path of the Julia interpreter by typing `which julia` in a console, for example, `/usr/bin/julia`. Be sure that the file is executable (e.g. `chmod 755 myscript.jl`). Then you can run the script with `./myscript.jl`;

4. Use an Integrated Development Environment (such as [Juno](include("test_script.jl") or [Jupiter](http://jupyter.org/)), open your Julia script and use the run command of the editor.

Julia keeps many things in memory within the same work session, so if this creates problems in the execution of your code, you can restart Julia. You can also use the [Revise.jl](https://github.com/timholy/Revise.jl) package for a finer control over what Julia keeps in memory during a work session.

You can check which version of Julia you are using with `versioninfo().`

## Packages

Many functions are provided in Julia by external "packages". The "standard library" is a package that is shipped with Julia itself, but like normal packages the user is required to manually load the standard library. Many standard features that were in the language core before Julia 1.0 have been moved to the standard library, so if you're moving from an older version of Julia be aware of this.

To include a Julia package's functionality in your Julia code, you must write `using Pkg` to use `Pkg`'s capabilities (alternatively, only for the package module, you can type `]` to enter a "special" Pkg mode).

You can then run the desired command, directly if you are in a terminal, in the Pkg mode, or `pkg"cmd to run"` in a script (notice that there is no space between `pkg` and the quoted command to run).

Some useful package commands:

1. `status` Retrieves a list with name and versions of locally installed packages
2. `update` Updates your local index of packages and all your local packages to the latest version
3. `add myPkg` Automatically downloads and installs a package
4. `rm myPkg` Removes a package and all its dependent packages that has been installed automatically only for it
5. `add pkgName#master`Checkouts the master branch of a package (and `free pkgName` returns to the released version)
6. `add pkgName#branchName`Checkout a specific branch
7. `add git@github.com:userName/pkgName.jl.git` Checkout a non registered pkg

To use the functions provided by a package, just include a `using mypackage` statement in the console or at the beginning of the script. If you prefer to import the package but keep the namespace clean, use `import mypackage`(you will then need to refer to a package function as `myPkg.myFunction`). You can also include other files using `include("MyFile.jl")`: when that line is run, the included file is completely ran (not only parsed) and any symbol defined there becomes available in the namespace relative to where include has been called.

`Winston` or `Plots` (plotting) and `DataFrames` (R-like tabular data) are example of packages that you will pretty surely want to consider.

For example (see the [Plotting]() section for specific Plotting issues):

## Troubleshooting

If you have any trouble with the above installation, here are some tips:

1. If you're having trouble with a package, you can try rebuilding it by doing `Pkg.build("PackageName")`, and you can also `Pkg.rm("PackageName"); Pkg.add("PackageName")` to remove it and add it back.
2. Do `using PyCall; PyCall.python` to see which Python executable your installation is using. You want it to be in a directory with `Anaconda3` or `anaconda3` in the path string.
3. If your error message includes something about GR, you might need to rebuild your GR package or use PyPlot instead (these are both _backends_ for Plots, meaning that they are used to generate the figures corresponding to your Plots commands). To rebuild GR, try `Pkg.update(); ENV["GRDIR"] = ""; Pkg.build("GR")`. To switch to PyPlot, try `Pkg.add("PyPlot"); Pkg.add("LaTeXStrings"); using Plots; pyplot()`.
4. Try googling the error message. Other folks have probably had similar issues, and sometimes the fix is pretty easy.
5. If you have Windows 7, there are instructions on the downloads page for stuff you have to do for Julia to work. One of these is the Windows Management Framework, which is necessary for Julia to be able to download binaries for its packages.

## Getting started 

You should complete the _Programming in Julia_ edX module to get oriented.

## startup.jl

If you don't want to have to run `using Statistics, LinearAlgebra` in every session, you can put these lines in your `startup.jl` file. The code in this file is loaded every time you run Julia.

The instructions below are for macOS/Linux. The same idea applies if you're using Windows, but the navigation commands are different. The basic idea is to put a `startup.jl` file in `~/.julia/config/`, where `~` represents whatever the home directory is on your system.

1. Open a Terminal session
2. Run `cd ~/.julia/`
3. Run `ls` to see if there is a `config` folder already there. If not, make one with `mkdir config`.
4. Run `cd config`
5. Run `emacs startup.jl` to create a `startup.jl` file and open an editor to put content into it.
6. Type `using Statistics, LinearAlgebra` and then save the file with `Ctrl-x Ctrl-s` (hold control and press `x`, then release and press `s`)
7. Close the editor with `Ctrl-x Ctrl-c`

[1]: https://julialang.org/downloads/




[Source](http://www.math.brown.edu/~sswatson/teaching.html "Permalink to Teaching")

# Teaching

[ ![][1]][2]

* [Research][3]
* [Teaching][4]
* [Resume][5]
* [Code][6]
* [About][7]
* [ ![][8]![][9]][10]

## Resources

* [Teaching Technology][11]

## Courses

* [DATA 2040 (deep learning)][12] (Spring 2019)
* [DATA 1010 (math for data science)][13] (Fall 2018)
* [Math 0350 (multivariable calculus) at Brown][14] (Fall 2017)
* [Math 0520 (linear algebra) at Brown][15] (Spring 2017)
* [Math 0190 (calculus+complex+DE+Fourier) at Brown][16] (Fall 2016)
* [Math 1610 (probability) at Brown][17] (Fall 2015)
* [Recitation for 18.022 Multivariate Calculus at MIT][18] (Fall 2014)

## Contests and Clubs

* MIT Integration Bee ([2013][19], [2014][20])
* [Ole Miss High School Math Contests][21] (2005–2008)

[1]: http://www.math.brown.edu/~sswatson/img/ustface.png
[2]: http://www.math.brown.edu/~sswatson/index.html
[3]: http://www.math.brown.edu/~sswatson/research.html
[4]: http://www.math.brown.edu/~sswatson/teaching.html
[5]: http://www.math.brown.edu/~sswatson/resume.html
[6]: http://www.math.brown.edu/~sswatson/code.html
[7]: http://www.math.brown.edu/~sswatson/about.html
[8]: http://www.math.brown.edu/~sswatson/img/glass.svg
[9]: http://www.math.brown.edu/~sswatson/img/glass_light.svg
[10]: http://www.math.brown.edu/~sswatson/search.html
[11]: http://www.math.brown.edu/teachingtechnology/
[12]: http://www.math.brown.edu/classes/data2040/
[13]: http://www.math.brown.edu/classes/data1010/
[14]: http://www.math.brown.edu/classes/math0350/index.html
[15]: http://www.math.brown.edu/classes/math0520/index.html
[16]: http://www.math.brown.edu/classes/math0190/index.html
[17]: http://www.math.brown.edu/classes/math1610/index.html
[18]: http://www.math.brown.edu/classes/math18022/index.html
[19]: http://www.math.brown.edu/contests/integrationbee/2013.html
[20]: http://www.math.brown.edu/contests/integrationbee/2014.html
[21]: http://www.math.brown.edu/contests/umcontest/index.html

  



  