
[Source](http://www.math.brown.edu/~sswatson/classes/data1010/setup.html "Permalink to Julia setup"). This page is converted to markdown from html by using  [WELCOME TO FUCK YEAH MARKDOWN]( http://fuckyeahmarkdown.com )

This page is taken from (http://www.math.brown.edu/~sswatson/classes/data1010/setup.html). It has lot of good resources concerning mathematics and Julia. Please check this page.

# Julia setup

## Download

You can download Julia from http://julialang.org/downloads. I recommend Julia 1.0.1 for this class. Also, use the standard download link you see on that page, rather than JuliaPro or any other distribution.

## Julia and Python

If you have Anaconda installed on your machine, you will want to point the IJulia and PyCall packages to your Anaconda executables so that it doesn't install its own versions (replace `sswatson` with your own username on your machine—also, you will want to check that you have Anaconda installed in the same place I do). You have to re-build the packages after updating the `ENV` dictionary.

**Step 1.** _Find your Anaconda Python executable._ Launch an Anaconda Python session and from within that session run
    
    

    import sys
    sys.executable


Make note of this path.

**Step 2.** _Find your Jupyter executable_. On a Mac, run `which jupyter` from a Terminal session get the path of your Jupyter executable. It's probably somewhere like `/Users/sswatson/anaconda3/bin/jupyter`. On Windows, it's probably somewhere like `C:/Users/sswatson/Anaconda3/Scripts/jupyter`. You can check this by starting Command Prompt, typing `cd Ana` and pressing tab to see if it autocompletes to `cd Anaconda3`. Then start typing `Scripts` and hit tab again to see that it completes to `Scripts`.

**Step 3.** [_Download Julia][1] and run the following from a Julia session._ Replace the Jupyter and Python paths below with what you found in Steps 1 and 2.
    
    

    using Pkg
    ENV["JUPYTER"] = "/Users/sswatson/anaconda3/bin/jupyter"
    Pkg.build("IJulia")
    ENV["PYTHON"] = "/Users/sswatson/anaconda3/bin/python"
    Pkg.build("PyCall")

**Step 4.** We will also be using the `Plots` package and a few others, so you can go ahead and run `julia Pkg.add("Plots") Pkg.add("Images") Pkg.add("Colors")` If you don't install these now, you can install them later.



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



## Adding a Package

To add a package use

`] add DSP`

and after installing, to exist use


​    





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

  



  