# Singularity R: rstudio

[![https://www.singularity-hub.org/static/img/hosted-singularity--hub-%23e32929.svg](https://www.singularity-hub.org/static/img/hosted-singularity--hub-%23e32929.svg)](https://singularity-hub.org/collections/798)
[![GitHub License](https://img.shields.io/badge/license-MIT-green.svg)](https://opensource.org/licenses/MIT)


Singularity image for [RStudio Desktop](https://www.rstudio.com/products/RStudio/) based on the [r-base](https://hub.docker.com/_/r-base/) docker image.

## Build

You can build a local Singularity image named `rstudio.3.4.4.simg` with:

```
$ sudo singularity build rstudio.3.4.4.simg Singularity
```

## Deploy

Instead of building it yourself you can download the pre-built image from
[Singularity Hub](https://www.singularity-hub.org) with:

```bash
singularity pull --name rstudio.3.4.4.simg shub://mjstealey/rstudio
```

## Usage

Help

```console
$ singularity help rstudio.3.4.4.simg


  RStudio Desktop version 1.1.442
  R version 3.4.4 (2018-03-15) -- "Someone to Lean On"

  Usage:
  $ singularity run rstudio.3.4.4.simg [args]
  $ singularity run --app R rstudio.3.4.4.simg [args]
  $ singularity run --app Rscript rstudio.3.4.4.simg [args]
  $ singularity run --app rstudio rstudio.3.4.4.simg
```

## Run



No particular command is launched using the default run command, rather it is left to the user to specify:

```bash
singularity run rstudio.3.4.4.simg [args]
```

Where `[args]` is generally one of {`rstudio`, `R [args]`, `Rscript [args]`}

### R

The `R` command is launched as an explicit app:

```bash
singularity run --app R rstudio.3.4.4.simg [args]
```

Example:

```console
$ singularity run --app R rstudio.3.4.4.simg --version
R version 3.4.4 (2018-03-15) -- "Someone to Lean On"
Copyright (C) 2018 The R Foundation for Statistical Computing
Platform: x86_64-pc-linux-gnu (64-bit)

R is free software and comes with ABSOLUTELY NO WARRANTY.
You are welcome to redistribute it under the terms of the
GNU General Public License versions 2 or 3.
For more information about these matters see
http://www.gnu.org/licenses/.
```

### Rscript

The `Rscript` command is launched as an explicit app:

```bash
singularity run --app Rscript rstudio.3.4.4.simg [args]
```

Example:

```console
$ singularity run --app Rscript rstudio.3.4.4.simg --version
R scripting front-end version 3.4.4 (2018-03-15)
```

### RStudio

The `rstudio` command is launched as an explicit app:

```bash
singularity run --app rstudio rstudio.3.4.4.simg
```

Example:

```console
$ singularity run --app rstudio rstudio.3.4.4.simg
libGL error: No matching fbConfigs or visuals found
libGL error: failed to load driver: swrast
```

**RStudio Desktop UI**: (using X11)

<img width="80%" alt="RStudio Desktop" src="https://user-images.githubusercontent.com/5332509/37848039-221fdf5e-2ea9-11e8-8f9c-db199ad4f6d2.png">


**NOTE**: 

- The `LibGL error:` errors were observed while testing using a remote CentOS 7 VM to run the Singularity image and the UI was rendered using X11. No other errors were denoted during testing. 
- On exit, the terminal displayed: 

    ```console
    QApplication::qAppName: Please instantiate the QApplication object first`
    ```

## Contributing

Bug reports and pull requests are welcome on GitHub at [https://github.com/mjstealey/rstudio](https://github.com/mjstealey/rstudio).

## License

The code is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).
