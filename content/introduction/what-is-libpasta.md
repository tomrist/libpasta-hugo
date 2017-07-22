+++
title = "What is libpasta?"
toc = true
weight = 4
+++

#### _Making Passwords Painless_

This library aims to be a all-in-one solution for password storage. In
particular, we aim to provide:

 - Easy-to-use password storage with sane defaults.
 - Tools to provide parameter tuning for different use cases.
 - Automatic migration of password to new algorithms.
 - Cross-platform builds and cross-language bindings.

#### Secure by Default

`libpasta` is ready to work at a production level straight out of the box. We
hide any unnecessary decisions from the developer. Together with the support for
[migrating passwords](#easy-password-migration), `libpasta` gives you the
peace-of-mind to install once, and never touch it again.

Currently, the algorithm favoured by `libpasta` is XXX (probably scrypt).
For more details, see [algorithm choice](../../technical-details/algorithm-choice).


#### Easy password migration

We aim to help everyone move away from insecure password hashing systems, 
to more modern algorithms. Hence we have designed `libpasta` to come with 
built-in support for password migration.

This allows you to easily, and dynamically, migrate all password hashes to
secure algorithms, without inconveniencing users with password resets.

Furthermore, having convenient migration tools makes it easier to keep your
parameters selection up to date with increases in computer performance.

See [basic usage](../basic-usage#password-migration) for an example of 
migrating passwords, or [advanced usage](../../advanced/migration/) for more 
details.

#### Tuning tools

For times when the default parameters are not sufficient, `libpasta` helps to
pick the optimal parameters.

The tuning tool measures the performance of your system to suggest parameters.
As a safeguard, the tool also estimates the parameters based off of the 
specifications of the system, to avoid mistakenly suggesting lower parameters.

See [tuning](../../advanced/tuning) for more details.

#### Cross-platform and cross-language

While the main library is written in Rust, thanks to the C-style ABI that is
exported by Rust libraries, we are able to support many different languages.
Similarly, Rust supports compilation over a number of platforms.

For more information, see [other languages](../../other-languages).