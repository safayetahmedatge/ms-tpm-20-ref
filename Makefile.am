#;**********************************************************************;
# Copyright (c) 2017 Intel Corporation
# All rights reserved.
#
# Redistribution and use in source and binary forms, with or without 
# modification, are permitted provided that the following conditions are met:
# 
# 1. Redistributions of source code must retain the above copyright notice, 
# this list of conditions and the following disclaimer.
# 
# 2. Redistributions in binary form must reproduce the above copyright notice, 
# this list of conditions and the following disclaimer in the documentation 
# and/or other materials provided with the distribution.
# 
# THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" 
# AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE 
# IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE 
# ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE 
# LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR 
# CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF 
# SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS 
# INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN 
# CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) 
# ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF 
# THE POSSIBILITY OF SUCH DAMAGE.
#;**********************************************************************;

PLATFORM_INC = -I TPMCmd/Platform/include -I TPMCmd/Platform/include/prototypes
TPM_INC = -I TPMCmd/tpm/include -I TPMCmd/tpm/include/prototypes

libplatform = TPMCmd/Platform/src/libplatform.a
noinst_LIBRARIES = $(libplatform)

TPMCmd_Platform_src_libplatform_a_CFLAGS = $(PLATFORM_INC) $(TPM_INC)
TPMCmd_Platform_src_libplatform_a_SOURCES = " \
    TPMCmd/Platform/include/PlatformData.h \
    TPMCmd/Platform/include/prototypes/Platform_fp.h \
    TPMCmd/Platform/src/Cancel.c \
    TPMCmd/Platform/src/Clock.c \
    TPMCmd/Platform/src/Entropy.c \
    TPMCmd/Platform/src/Fail.c \
    TPMCmd/Platform/src/LocalityPlat.c \
    TPMCmd/Platform/src/NVMem.c \
    TPMCmd/Platform/src/PlatformData.c \
    TPMCmd/Platform/src/PowerPlat.c \
    TPMCmd/Platform/src/PPPlat.c \
    TPMCmd/Platform/src/RunCommand.c \
    TPMCmd/Platform/src/Unique.c \
"
