Nbdev-ignore
================

<!-- WARNING: THIS FILE WAS AUTOGENERATED! DO NOT EDIT! -->

## Install

``` sh
pip install nbdev_ignore
```

# How it works

There’s only one function
[`ignore_`](https://feynlee.github.io/nbdev-ignore/core.html#ignore_) in
this module. It’s exactly the same as the [hide\_]() processor in
`nbdev`, so that “\#\| ignore” serves the same purpose as “\#\| hide”.
For details on how it works, see []().

In order for it to also serve as a test flag, we will need to manually
add it to `tst_flags` (see below), as currently there’s no way to plug
it into the `nbdev_test` process.

## How to use

To enable the `#| ignore` directive, in your settings.ini make sure to:

- Add `nbdev_ignore` as a requirement
- Add `procs = nbdev_igore.core:ignore_`, where it should point to the
  exact function being called
- Add it to test flags: `tst_flags = ignore`, so that cells with this
  directive also avoids testing. If you already have other test flags,
  separate them with space. For example, if you already have `notest` as
  your test flag, then `tst_flags = notest ignore`.
