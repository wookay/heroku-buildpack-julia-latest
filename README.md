# Julia Nightly buildpack for Heroku

This is a Heroku buildpack for adding a [Julia binary][1] to your environment.

## Versions

* Buildpack: `0.2`
* Julia: `latest`

## Usage

Add this line to the .buildpacks file in your project:

`https://github.com/wookay/heroku-buildpack-julia-latest.git`

or use the command `heroku buildpacks:set`

In your project, create a file `package.jl` with any
Julia code you want to run after installation.
E.g. to add Bukdu support:
```julia
using Pkg
Pkg.REPLMode.pkgstr("add HTTP#master")
Pkg.REPLMode.pkgstr("add https://github.com/wookay/Bukdu.jl.git#sevenstars")
using Bukdu
```


* the original code from https://github.com/pinx/heroku-buildpack-julia

[1]: https://julialang.org
