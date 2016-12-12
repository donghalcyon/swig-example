# SWIG Example

This is an example of how to use CMake with the [SWIG](http://www.swig.org) interface generator. It is meant for those
interested to use as a guide to setting up a project built by CMake with interfaces in other languages generated by
SWIG.

### Languages
This example currently generates interfaces for the following languages:

* Python

I will add languages as I need to use them. Anyone that wishes to add another language, feel free to open a pull request
and let me know if there are any issues with using the installation procedure described below with your language.

### Installation
A large part of this example is how to install both the C/C++ libraries that SWIG is wrapping as well as the generated
wrappers. After a good bit of trying different approaches, the following is the current approach:

---

##### C/C++ Libraries
C/C++ libraries are installed with the standard `make install` command with `install` targets in the CMake
configuration.

##### Wrapper Libraries
Wrapper library installation of both the C libraries and target language libraries generated by SWIG are handled by
the target language's packaging system. In addition, a target `make-<LANGUAGE>` is added to the CMake configuration
to run anything that needs to be run in the target language.

---

It is planned to have `make-<LANGUAGE>` install the C/C++ libraries in a language-specific directory, but that
functionality has not yet been added.