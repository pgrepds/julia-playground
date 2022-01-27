# Playground for the Julia Programming Language

The following repository contains code for exploring the Julia programming language.

## Linux setup

The installation on my Manjaro Linux machine is straight forward. We execute the following command.

```bash
sudo pacman -S julia
```

We should be able to run Julia now by executing the following command.

```bash
julia
```

We could execute Julia commands directly in the terminal. Let us use the classic "Hello World" example which is straight forward as well.

```julia
julia> print("Hello World")
```

In order to exit the 'Julia' environment just run the following command.

```julia
julia> exit()
```

Next, we create a file called 'hello.jl' and append the same command in it by using a standard text editor or by piping the command line directly.

We can run this file as follows.

```bash
julia hello.jl
```

## Julia packages and using Jupyter

If we want to import julia packages, there are several ways to achieve this. First, we enter the julia terminal environment once again.

```bash
julia
```

Then, we run the following command.

```
julia> using Pkg
```

`Pkg` is Julia's builtin package manager. A more in-depth documentation can be found on the [Julia webpage](https://docs.julialang.org/en/v1/stdlib/Pkg/).

In order to add a package for using the Jupyter Kernel for Julia we execute the following command.

```julia
julia> Pkg.add("IJulia")
```

If we want to remove a package, we simply execute the following command.

```julia
julia> Pkg.rm("IJulia")
```

Updating the packages is pretty straight forward. We execute the following command.

```julia
julia> Pkg.update()
```

There is also a different way for interacting with the Julia package manager. Enter `]` in the Julia command environment in order to enter the package manager environment.

Every command can now be used directly without using `Pkg` (e.g. instead of saying `Pkg.update()` we can simply say `update()`). Typing the `backspace` once, brings us back to the Julia command prompt.

Starting a new notebook is achieved by executing the following command.

```julia
julia> notebook()
```

If we choose to use JupyterLab (a more "IDE" like experience) instead, we execute the following command.

```julia
julia> jupyterlab()
```

More in-depth information can be found in the official [IJulia documentation](https://juliahub.com/ui/Packages/IJulia/nfu7T/1.21.2).

## Pluto

There is a Jupyter environment on steroids called [Pluto.jl](https://github.com/fonsp/Pluto.jl) for the Julia programming language which looks very promising (e.g. changing one cell instantly updates all other cells referencing code from this cell, which seems to be a major advantage compared to "normal" Jupyter notebooks).

We can use it by adding the following package.

```julia
julia> ]
(@v1.7) pkg> add Pluto
```

We import and run the Pluto environment as follows.

```julia
julia> import Pluto
julia> Pluto.run()
```

Notice that by design outputs of the `print` command will not show inside the notebook but in the terminal. If we want to change this, then could use the `PlutoUI` package.

```julia
julia> ]
(@v1.7) pkg> add PlutoUI
julia> using PlutoUI
```

Notice that we can also run `using PlutoUI` in a Pluto cell, which will do the exact same thing as the commands entered above.

We can use the following command in a Pluto cell now.

```julia
Print("Hello World")
```

## VSCode

We can also use a Julia notebook (or Julia in general) in VSCode using the offical Julia extension, which is my preferred way of using Julia.

This usage is straight forward as well. We create a new '.ipynb' file and select the Julia extension (or the local installation) as the Jupyter kernel and we are ready to go.
