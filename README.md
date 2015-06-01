Poudriere Utils
===============

This repository contains some shell scripts that simplifies the management of
Poudriere jails.  The `poudriere-utils.sh` script is a thin wrapper above the
`poudriere` scripts that takes care of sensible defaults such as:

  * Create a default Makefile and package list for each `poudriere` jail it
    creates.

  * Use intuitive defaults for the `poudriere` commands it wraps.


Usage
-----

The `poudriere-utils.sh` scripts accepts the following command syntax:

    $ poudriere-utils.sh command [options]*

The `poudriere-utils.sh` scripts currently supports the following commands:

  * `create`: Creates a new jail.

  * `delete`: Deletes an existing jail.

  * `help`: Shows the help message.

  * `run`: Executes a _bulk_ build.

The command `options` are command-specific.  The help message of any command can
be shown using the `-h` option:

    $ poudriere-utils.sh create -h

----

Copyright (c) 2015 Enrico Maria Crisostomo

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