# Embedded Envoy Example

Starting point for creating a new project/repository that aims to
embed Envoy (in a C/C++ binary) by leveraging a fork of Envoy that
provides a Bazel target that doesn't include a `main()`.

Details:

* Clone the repository with `git clone --recurse-submodules ...` or
  after cloning do a `git submodule update --init`.

* Envoy (and/or some of it's dependencies) require a specific Bazel
  version, specified in `.bazelversion`.

* Envoy expects certain build attributes thus our `.bazelrc` imports
  the one from Envoy. Also, the `workspace_status_command` must be
  properly set up to point to the one provided by Envoy.

* `WORKSPACE` needs to initialize Envoy. NOTE: you ***can't*** use the
  `.bazel` extension to `WORKSPACE` because some of the dependencies
  look for just a `WORKSPACE` file but not a `WORKSPACE.bazel` file.

See `main.cc` for usage and `BUILD.bazel` for the Bazel target on
which to depend.



