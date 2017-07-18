+++
title = "Serializing Hashes"
toc = true
weight = 5

+++

We use the PHC string format, as defined [here](https://github.com/P-H-C/phc-string-format/blob/master/phc-sf-spec.md), to
format password hashes produced by libpasta.

These take the following format:

       $<id>[$<param>=<value>(,<param>=<value>)*][$<salt>[$<hash>]]

where:

 - `<id>` is the symbolic name for the function
 - `<param>` is a parameter name
 - `<value>` is a parameter value
 - `<salt>` is an encoding of the salt
 - `<hash>` is an encoding of the hash output

The string is then the concatenation, in that order, of:

 - a `$` sign;
 - the function symbolic name;
 - optionally, a `$` sign followed by one or several parameters, each
   with a `name=value` format; the parameters are separated by commas;
 - optionally, a `$` sign followed by the (encoded) salt value;
 - optionally, a `$` sign followed by the (encoded) hash output (the
   hash output may be present only if the salt is present).
