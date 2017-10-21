Poudriere Utils
===============

This repository contains some shell scripts that simplifies the management of
Poudriere jails.  The `poudriere-utils` script is a thin wrapper around the
`poudriere` script that takes care of sensible defaults such as:

  * Creating a default Makefile and package list for each `poudriere` jail it
    creates.

  * Using intuitive defaults instead of requiring the user to specify a lot of
    options.

Defaults
--------

Many `poudriere` commands require the user to specify a certain number of
options, and for very vew of them a sensible default value is inferred.  The
most used options are:

  * The jail you are working on.

  * The ports tree the jail shall use (unless there is only one ports tree named
    `default`).

  * The name of the file containing the list of ports to build.

`poudriere-utils` simplifies your workflow making the following assumptions:

  * By default, a jail is named after the FreeBSD version and the architecture:

        JAIL_NAME=${VERSION}${ARCH}

    where `${VERSION}` is the FreeBSD version stripped of any non-digit
    character (`10.1-RELEASE` will become `101`).

  * By default, a jail Makefile fragment is named after the jail:

        ${POUDRIERE_ETC}/${JAIL_NAME}-make.conf

  * By default, the file containing the list of ports to build on a jail is
    named after the jail:

        ${POUDRIERE_ETC}/${JAIL_NAME}-pkglist

  * If only a jail exists, it is assumed to be the default jail.

  * If only a ports tree exists, it is assumed to be the default ports tree.

In the previous examples, the variable `${POUDRIERE_ETC}` indicates the
`poudriere` configuration file location, that by default is:

    /usr/local/etc/poudriere.d

### Example

On a system with `amd64` architecture, the effect of the command:

    $ poudriere-utils create -v 10.1-RELEASE

will be:

  * Creating a jail named `101amd64`.

  * Creating an empty `${POUDRIERE_ETC}/101amd64-pkglist` file.

  * Creating the `${POUDRIERE_ETC}/101amd64-make.conf` file and append the
    following definition to it:

        WITH_PKG=yes

Installation
------------

`poudriere-utils` must be compiled and installed from the [latest release
tarball][latest]:

    $ ./configure
    $ make install

[latest]: https://github.com/emcrisostomo/poudriere-utils/releases/latest

Requirements
------------

`poudriere-utils` has the following requirements:

  * The Zsh shell.
  * Poudriere.

Usage
-----

The `poudriere-utils` scripts accepts the following command syntax:

    $ poudriere-utils command [options]*

The `poudriere-utils` scripts currently supports the following commands:

  * `create`: Creates a new jail.

  * `delete`: Deletes an existing jail.

  * `help`: Shows the help message.

  * `run`: Executes a _bulk_ build.

The command `options` are command-specific.  The help message of any command can
be shown using the `-h` option:

    $ poudriere-utils create -h

----

Copyright (c) 2015-2017 Enrico Maria Crisostomo

All rights reserved.

Redistribution and use in source and binary forms, with or without modification,
are permitted provided that the following conditions are met:

  * Redistributions of source code must retain the above copyright notice, this
    list of conditions and the following disclaimer.

  * Redistributions in binary form must reproduce the above copyright notice,
    this list of conditions and the following disclaimer in the documentation
    and/or other materials provided with the distribution.

  * Neither the name of poudriere-utils nor the names of its contributors may be
    used to endorse or promote products derived from this software without
    specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND
ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED
WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE FOR
ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES
(INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES;
LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON
ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
(INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS
SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
