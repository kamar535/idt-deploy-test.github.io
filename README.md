The public website for [Introduktion till datorer](https://introduktion-till-datorer.github.io/) at the [Faculty of Science and Technology](https://www.uu.se/en/students/faculty/science-and-technology) at [Uppsala university](https://www.uu.se/en) uses the static site generator [Hugo](https://gohugo.io/) and is hosted on [GitHub pages](https://pages.github.com/).

## Dependencies 

The latest versions of dependencies verified to be able to build this site are:

- [Go][go] version 1.24.1
- [Hugo v0.135.0][v0.135.0]
- Hugo Relearn theme [version 6][relearn-6], specifically the [82a5e9876c67] commit. 
- [Hugo theme Relearn tweaks v6.0.0][tweaks-6.0.0]. 

[go]: https://go.dev/

[v0.135.0]: https://github.com/gohugoio/hugo/releases/tag/v0.135.0

[82a5e9876c67]: https://github.com/McShelby/hugo-theme-relearn/commit/82a5e9876c67

[relearn-6]: https://mcshelby.github.io/hugo-theme-relearn/introduction/changelog/6/index.html

[ebc04a643c2]: https://github.com/kamar535/hugo-theme-relearn-tweaks/commit/ebc04a643c2d

[tweaks-6.0.0]: https://github.com/kamar535/hugo-theme-relearn-tweaks/releases/tag/v6.x

## Subsites

Each year subsites are added for the Swedish and English verisons of the site. 

## Common configuration

Configuration common to all sites are kept in the `hugo.toml` in the `github.com/kamar535/hugo-theme-relearn-tweaks` module. 

## Site specific configuration

Each subsite has its own `hugo.toml` with subsite specific configuration. 

## Combining multiple configuration files

Two or more configuration files can be combined with left-to-right precedence:

```
hugo --config a.toml, b.toml, c.toml
```

In the above example settings in `a.toml` as the highest precedence and will override settings in `b.toml` and `c.toml`.

## Build specific subsites

To build a specific subsite, use `hugo` from the root directory togheter with the config for the site. 

For example, to build the Swedish 2024 site: 

```
hugo server --config=2024/hugo.toml hugo.toml
```

For example, to build the English 2024 site: 

```
hugo server --config=2024-eng/hugo.toml hugo.toml
```


## GitHub pages 

The site is hosted on [GitHub pages](https://pages.github.com/). When a new subiste is added you must add build rules in `.github/workflows/hugo.yaml`. Read more here:

- https://gohugo.io/host-and-deploy/host-on-github-pages/

## Hugo Go Modules

One way to share parts of a Hugo sites between different projects is using [Hugo
modules](https://gohugo.io/hugo-modules/). 

Read more: 

- [Using Hugo Modules Instead of Git Submodules](https://www.adamormsby.com/posts/012-hugo-modules/)

## Initialize the project as a Hugo module

**Note:** This only applies the first time you add modules to your Hugo project. 

Before starting using Hugo modules in a project you must first initialize the project as a Hugo module. 

Check if you already have Go installed: 

```
go version
```

If you don't have Go installed, [download and install
Go](https://go.dev/doc/install). 

Next, [initialize the project as a Hugo Module](https://gohugo.io/commands/hugo_mod_init/). The module must be given a unique identifier. A common practice is to use the GitHub repo URL, for example:


```
hugo mod init github.com/<your_user>/<your_project>
```

, but any string seems to work. 

On sucess, the [go.mod](https://go.dev/doc/modules/gomod-ref) file is created. 


## Theme Relearn and Theme Relearn Tweaks

Once you have created the `go.mod` file you can add a Hugo theme as a Hugo
module instead of including the theme as a git submodule.

In the `hugo.toml` the Hugo Relearn theme and the Hugo Relearn Tweaks modules are imported.a

```
# Modules on the bottom will get loaded first, so keep anything you don’t want
# overridden higher up in the module chain. All conflicting files during module
# import will use the last file loaded. 

[module]
    [[module.imports]]
        path = "github.com/kamar535/hugo-theme-relearn-tweaks"
    [[module.imports]]
        path = "github.com/McShelby/hugo-theme-relearn"

````


**Note:** If you add this to `hugo.toml` before initializing the project as a Hugo module
you will get an error. 


## Update modules

**Note:** Only do this when you want to update the site to use the latest versions of the imported modules. 

To get references to the latest version of each module and save these in 'go.mod':

```
hugo mod get
```

Keep in mind that the stored module references in `go.mod`` are references to a
specific commit on a github repo, not a branch. 

## Make and test changes in a module

One way to do local development of a module imported in a project is to add a
replace directive to a local directory with the source in `go.mod` as described
[here](https://gohugo.io/hugo-modules/use-modules/#make-and-test-changes-in-a-module).

Instead of modifying the `go.mod` files, you can also use the modules
configuration replacements option as described [here](https://gohugo.io/hugo-modules/configuration/#module-configuration-top-level).


## Know issues

A collection of know issues. 

### Permission denied errors with the Relearn theme

With the `5.27.0 (2024-04-07)` version of the Relearn Hugo theme I can only
run Hugo with the  `-–renderToMemory` flag, otherwise I get permission denied
errors. 

- [Hugo forum discussion](https://discourse.gohugo.io/t/can-only-run-hugo-with-rendertomemory-otherwise-gets-permission-denied-errors-even-after-chmod-a-rwx/49335)  
- [GitHub issue 831](https://github.com/McShelby/hugo-theme-relearn/issues/831)
  - After reading the [issues
linked](https://github.com/McShelby/hugo-theme-relearn/issues/831#issuecomment-2061733009)
by [jmooring](https://github.com/jmooring):

    -  I've tried running ` hugo --noChmod `
but I still get the same permission errors.  

    -  But, setting `themeVariantModifier = ".gen"` in the `[params]` section in `hugo.toml` as described in the theme [Configuration](https://mcshelby.github.io/hugo-theme-relearn/basics/configuration/index.html#annotated-config-options) section of the theme Relearn documentation  worked fine.  I'm happy this workaround exists but at the same time appreciate that the  root cause will  be fixed in the next release of the Relearn theme. 





