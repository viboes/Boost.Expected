Expected
========
A library for expected objects for C++14. This is the reference implementation of proposal NXXXX 
(see see https://github.com/ptal/std-expected-proposal). 
Expected has not been proposed yet to the C++ standard committee. 

Test results
-------------------

Branches        | Build         | Tests coverage
----------------|-------------- | -------------
Master:        | [![Build Status](https://travis-ci.org/viboes/Boost.Expected.svg?branch=master)](https://travis-ci.org/viboes/Boost.Expected)  | [![Coverage Status](https://coveralls.io/repos/viboes/Boost.Expected/badge.png?branch=master)](https://coveralls.io/r/viboes/Boost.Expected?branch=master)


Supported compilers
-------------------
* Clang 3.2
* G++ 4.8.0 (and probably later)
* VS14 CTP 3. Note that this compiler cannot do enough constexpr for Expected (or Boost for that matter) to turn it on, but it appears that MSVC doesn't mind and all unit tests pass anyway. It is possible VS14 RTM will do enough constexpr that it can be turned on.
* VS2013 which has the same limitations as VS14 (no constexpr). This uses an unrestricted union emulation which works well enough.

Usage
-----
For usage examples and the overview see https://github.com/ptal/std-expected-proposal

Differences from NXXXX
----------------------
* The constructor taking initializer_list argument is not constexpr. This is because initializer_list operations are not constexpr in C++11.
* Member function value_or does not have rvalue reference overload in GCC inferior to 4.8.1. This is because rvalue overloading on *this is not supported until GCC 4.8.1.
