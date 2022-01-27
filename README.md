# Playground for the Julia Programming Language

The following repository contains code for exploring the Julia programming language.

## Linux setup

The installation on my Manjaro Linux machine is straight forward. We execute the following command.

```
sudo pacman -S julia
```

We should be able to run Julia now by executing the following command.

```
julia
```

We could execute Julia commands directly in the terminal. Let us use the classic "Hello World" example which is straight forward as well.

```
print("Hello World")
```

In order to exit the 'Julia' environment just run the following command.

```
exit()
```

Next, we create a file called "hello.jl" and append the same command in it by using a standard text editor or by piping the command line directly.

We can run this file as follows.

```
julia hello.jl
```

## Julia packages

If we want to import julia packages, there are several ways to achieve this. First, we enter the julia terminal environment once again.

```
julia
```

Then, we run the following command.

```
using Pkg
```

`Pkg` is Julia's builtin package manager. A more in-depth documentation can be found on the [Julia webpage](https://docs.julialang.org/en/v1/stdlib/Pkg/).

In order to add a package for using Julia with a Jupyter notebook, well known in the world of Python, we execute the following command.

```
Pkg.add("IJulia")
```

If we want to remove a package, we simply execute the following command.

```
Pkg.rm("IJulia")
```

Updating the packages is pretty straight forward. We execute the following command.

```
Pkg.update()
```

There is also a different way for interacting with the Julia package manager. Enter `]` in the Julia command environment in order to enter the package manager environment.
