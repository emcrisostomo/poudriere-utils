#                                               -*- Autoconf -*-
# Copyright (C) 2015-2017 Enrico M. Crisostomo <enrico.m.crisostomo@gmail.com>
# All rights reserved.
#
# Redistribution and use in source and binary forms, with or without
# modification, are permitted provided that the following conditions are met:
#
#   * Redistributions of source code must retain the above copyright notice,
#     this list of conditions and the following disclaimer.
#
#   * Redistributions in binary form must reproduce the above copyright notice,
#     this list of conditions and the following disclaimer in the documentation
#     and/or other materials provided with the distribution.
#
#   * Neither the name of the copyright holder nor the names of its contributors
#     may be used to endorse or promote products derived from this software
#     without specific prior written permission.
#
# THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
# AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
# IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
# DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE
# FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
# DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
# SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
# CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
# OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
# OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
#
# Process this file with autoconf to produce a configure script.
dnl Copyright (C) 20145 Enrico M. Crisostomo
AC_PREREQ([2.69])
AC_INIT([poudriere-utils], [1.0.0], [enrico.m.crisostomo@gmail.com])
AC_COPYRIGHT([2015-2017 (C) Enrico M. Crisostomo])
AC_REVISION([$Revision: 1$])
AC_CONFIG_SRCDIR([LICENSE])
AC_CONFIG_AUX_DIR([config])
AC_CONFIG_HEADERS([config.h])
AC_CONFIG_FILES([Makefile])
AC_CONFIG_FILES([src/poudriere-utils],          [chmod +x src/poudriere-utils])
AC_CONFIG_FILES([src/poudriere-utils-create],   [chmod +x src/poudriere-utils-create])
AC_CONFIG_FILES([src/poudriere-utils-delete],   [chmod +x src/poudriere-utils-delete])
AC_CONFIG_FILES([src/poudriere-utils-bulk],     [chmod +x src/poudriere-utils-bulk])
AC_CONFIG_FILES([src/poudriere-utils-testport], [chmod +x src/poudriere-utils-testport])
AC_CONFIG_MACRO_DIR([m4])

AM_INIT_AUTOMAKE([-Wall -Werror foreign])

# Checks for programs.
EMC_PATH_PROG([ZSH_PATH],       [zsh],       [], [AC_MSG_ERROR(This script requires zsh.)],       [ZSH path])
EMC_PATH_PROG([POUDRIERE_PATH], [poudriere], [], [AC_MSG_ERROR(This script requires poudriere.)], [Poudriere path])

AC_OUTPUT
