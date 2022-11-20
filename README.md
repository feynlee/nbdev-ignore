Nbdev-ignore
================

<!-- WARNING: THIS FILE WAS AUTOGENERATED! DO NOT EDIT! -->

## Install

``` sh
pip install nbdev_ignore
```

# What this is

When using the [nbdev](https://github.com/fastai/nbdev) library, I often
find myself having to write

``` python
#| hide
#| eval: false
...
```

in order for that cell in Jupyter Notebook to be ignored by both the
tests and docs. It would great to have a simple directive to do this,
and this is the ignore directive:

``` python
#| ignore
...
```

It’s equivalent to the above directives.

## How to use

To enable the `#| ignore` directive, in your settings.ini make sure to:

- Add `nbdev_ignore` as a requirement
- Add `procs = nbdev_igore.core:ignore_`, where it should point to the
  exact function being called
- Add it to test flags: `tst_flags = ignore`, so that cells with this
  directive also avoids testing. If you already have other test flags,
  separate them with space. For example, if you already have `notest` as
  your test flag, then `tst_flags = notest ignore`.

## How it works

There’s only one function
[`ignore_`](https://feynlee.github.io/nbdev-ignore/core.html#ignore_) in
this module. It’s exactly the same as the [hide\_]() processor in
`nbdev`, so that “\#\| ignore” serves the same purpose as “\#\| hide”.
For details on how it works, see
[here](https://feynlee.github.io/nbdev-ignore/core.html).

In order for it to also serve as a test flag, we will need to manually
add it to `tst_flags` (see below) so tests will ignore cells with this
directive. Currently there’s no simple way to hack the `nbdev_test`
process, so this has to be done manually.
