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
SIMULATOR_INC =  -I TPMCmd/Simulator/include \
    -I TPMCmd/Simulator/include/prototypes
TPM_INC = -I TPMCmd/tpm/include -I TPMCmd/tpm/include/prototypes

libplatform = TPMCmd/Platform/src/libplatform.a
libtpm = TPMCmd/tpm/src/libtpm.a
tpm2_simulator = TPMCmd/Simulator/src/tpm2-simulator

bin_PROGRAMS = $(tpm2_simulator)
noinst_LIBRARIES = $(libplatform) $(libtpm)

TPMCmd_Platform_src_libplatform_a_CFLAGS = $(EXTRA_CFLAGS) $(PLATFORM_INC) \
    $(TPM_INC)
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

TPMCmd_Simulator_src_tpm2_simulator_CFLAGS = $(EXTRA_CFLAGS) $(PLATFORM_INC) \
    $(TPM_INC) $(SIMULATOR_INC) $(LIBCRYPTO_CFLAGS) $(PTHREAD_CFLAGS)
# the weird / duplicate static library is necessary for dealing with the
# circular dependency beetween libplatform and libtpm
TPMCmd_Simulator_src_tpm2_simulator_LDADD = $(libplatform) $(libtpm) \
    $(libplatform) $(LIBCRYPTO_LIBS) $(PTHREAD_LIBS)
TPMCmd_Simulator_src_tpm2_simulator_SOURCES = " \
    TPMCmd/Simulator/include/TpmTcpProtocol.h \
    TPMCmd/Simulator/src/TcpServer.c \
    TPMCmd/Simulator/src/TPMCmdp.c \
    TPMCmd/Simulator/src/TPMCmds.c \
"

TPMCmd_tpm_src_libtpm_a_CFLAGS = $(EXTRA_CFLAGS) $(PLATFORM_INC) $(TPM_INC) \
    $(LIBCRYPTO_CFLAGS)
TPMCmd_tpm_src_libtpm_a_SOURCES = " \
    TPMCmd/tpm/include/BaseTypes.h \
    TPMCmd/tpm/include/BnValues.h \
    TPMCmd/tpm/include/Capabilities.h \
    TPMCmd/tpm/include/CommandAttributeData.h \
    TPMCmd/tpm/include/CommandAttributes.h \
    TPMCmd/tpm/include/CommandDispatchData.h \
    TPMCmd/tpm/include/CommandDispatcher.h \
    TPMCmd/tpm/include/Commands.h \
    TPMCmd/tpm/include/CompilerDependencies.h \
    TPMCmd/tpm/include/CryptEcc.h \
    TPMCmd/tpm/include/CryptHash.h \
    TPMCmd/tpm/include/CryptRand.h \
    TPMCmd/tpm/include/CryptRsa.h \
    TPMCmd/tpm/include/CryptTest.h \
    TPMCmd/tpm/include/EccTestData.h \
    TPMCmd/tpm/include/Global.h \
    TPMCmd/tpm/include/GpMacros.h \
    TPMCmd/tpm/include/HandleProcess.h \
    TPMCmd/tpm/include/HashTestData.h \
    TPMCmd/tpm/include/Implementation.h \
    TPMCmd/tpm/include/InternalRoutines.h \
    TPMCmd/tpm/include/LibSupport.h \
    TPMCmd/tpm/include/ltc/LtcSettings.h \
    TPMCmd/tpm/include/ltc/TpmToLtcHash.h \
    TPMCmd/tpm/include/ltc/TpmToLtcMath.h \
    TPMCmd/tpm/include/ltc/TpmToLtcSym.h \
    TPMCmd/tpm/include/NV.h \
    TPMCmd/tpm/include/ossl/TpmToOsslHash.h \
    TPMCmd/tpm/include/ossl/TpmToOsslMath.h \
    TPMCmd/tpm/include/ossl/TpmToOsslSym.h \
    TPMCmd/tpm/include/PRNG_TestVectors.h \
    TPMCmd/tpm/include/prototypes/ActivateCredential_fp.h \
    TPMCmd/tpm/include/prototypes/AlgorithmCap_fp.h \
    TPMCmd/tpm/include/prototypes/AlgorithmTests_fp.h \
    TPMCmd/tpm/include/prototypes/Attest_spt_fp.h \
    TPMCmd/tpm/include/prototypes/Bits_fp.h \
    TPMCmd/tpm/include/prototypes/BnConvert_fp.h \
    TPMCmd/tpm/include/prototypes/BnMath_fp.h \
    TPMCmd/tpm/include/prototypes/BnMemory_fp.h \
    TPMCmd/tpm/include/prototypes/CertifyCreation_fp.h \
    TPMCmd/tpm/include/prototypes/Certify_fp.h \
    TPMCmd/tpm/include/prototypes/ChangeEPS_fp.h \
    TPMCmd/tpm/include/prototypes/ChangePPS_fp.h \
    TPMCmd/tpm/include/prototypes/ClearControl_fp.h \
    TPMCmd/tpm/include/prototypes/Clear_fp.h \
    TPMCmd/tpm/include/prototypes/ClockRateAdjust_fp.h \
    TPMCmd/tpm/include/prototypes/ClockSet_fp.h \
    TPMCmd/tpm/include/prototypes/CommandAudit_fp.h \
    TPMCmd/tpm/include/prototypes/CommandCodeAttributes_fp.h \
    TPMCmd/tpm/include/prototypes/CommandDispatcher_fp.h \
    TPMCmd/tpm/include/prototypes/CommandTiming_fp.h \
    TPMCmd/tpm/include/prototypes/Commit_fp.h \
    TPMCmd/tpm/include/prototypes/ContextLoad_fp.h \
    TPMCmd/tpm/include/prototypes/ContextSave_fp.h \
    TPMCmd/tpm/include/prototypes/Context_spt_fp.h \
    TPMCmd/tpm/include/prototypes/Create_fp.h \
    TPMCmd/tpm/include/prototypes/CreateLoaded_fp.h \
    TPMCmd/tpm/include/prototypes/CreatePrimary_fp.h \
    TPMCmd/tpm/include/prototypes/CryptDes_fp.h \
    TPMCmd/tpm/include/prototypes/CryptEccKeyExchange_fp.h \
    TPMCmd/tpm/include/prototypes/CryptEccMain_fp.h \
    TPMCmd/tpm/include/prototypes/CryptEccSignature_fp.h \
    TPMCmd/tpm/include/prototypes/CryptHash_fp.h \
    TPMCmd/tpm/include/prototypes/CryptPrime_fp.h \
    TPMCmd/tpm/include/prototypes/CryptPrimeSieve_fp.h \
    TPMCmd/tpm/include/prototypes/CryptRand_fp.h \
    TPMCmd/tpm/include/prototypes/CryptRsa_fp.h \
    TPMCmd/tpm/include/prototypes/CryptSelfTest_fp.h \
    TPMCmd/tpm/include/prototypes/CryptSym_fp.h \
    TPMCmd/tpm/include/prototypes/CryptUtil_fp.h \
    TPMCmd/tpm/include/prototypes/DA_fp.h \
    TPMCmd/tpm/include/prototypes/DictionaryAttackLockReset_fp.h \
    TPMCmd/tpm/include/prototypes/DictionaryAttackParameters_fp.h \
    TPMCmd/tpm/include/prototypes/Duplicate_fp.h \
    TPMCmd/tpm/include/prototypes/ECC_Parameters_fp.h \
    TPMCmd/tpm/include/prototypes/ECDH_KeyGen_fp.h \
    TPMCmd/tpm/include/prototypes/ECDH_ZGen_fp.h \
    TPMCmd/tpm/include/prototypes/EC_Ephemeral_fp.h \
    TPMCmd/tpm/include/prototypes/EncryptDecrypt2_fp.h \
    TPMCmd/tpm/include/prototypes/EncryptDecrypt_fp.h \
    TPMCmd/tpm/include/prototypes/EncryptDecrypt_spt_fp.h \
    TPMCmd/tpm/include/prototypes/Entity_fp.h \
    TPMCmd/tpm/include/prototypes/EventSequenceComplete_fp.h \
    TPMCmd/tpm/include/prototypes/EvictControl_fp.h \
    TPMCmd/tpm/include/prototypes/ExecCommand_fp.h \
    TPMCmd/tpm/include/prototypes/FieldUpgradeData_fp.h \
    TPMCmd/tpm/include/prototypes/FieldUpgradeStart_fp.h \
    TPMCmd/tpm/include/prototypes/FirmwareRead_fp.h \
    TPMCmd/tpm/include/prototypes/FlushContext_fp.h \
    TPMCmd/tpm/include/prototypes/GetCapability_fp.h \
    TPMCmd/tpm/include/prototypes/GetCommandAuditDigest_fp.h \
    TPMCmd/tpm/include/prototypes/GetRandom_fp.h \
    TPMCmd/tpm/include/prototypes/GetSessionAuditDigest_fp.h \
    TPMCmd/tpm/include/prototypes/GetTestResult_fp.h \
    TPMCmd/tpm/include/prototypes/GetTime_fp.h \
    TPMCmd/tpm/include/prototypes/Global_fp.h \
    TPMCmd/tpm/include/prototypes/Handle_fp.h \
    TPMCmd/tpm/include/prototypes/Hash_fp.h \
    TPMCmd/tpm/include/prototypes/HashSequenceStart_fp.h \
    TPMCmd/tpm/include/prototypes/HierarchyChangeAuth_fp.h \
    TPMCmd/tpm/include/prototypes/HierarchyControl_fp.h \
    TPMCmd/tpm/include/prototypes/Hierarchy_fp.h \
    TPMCmd/tpm/include/prototypes/HMAC_fp.h \
    TPMCmd/tpm/include/prototypes/HMAC_Start_fp.h \
    TPMCmd/tpm/include/prototypes/Import_fp.h \
    TPMCmd/tpm/include/prototypes/IncrementalSelfTest_fp.h \
    TPMCmd/tpm/include/prototypes/IoBuffers_fp.h \
    TPMCmd/tpm/include/prototypes/LoadExternal_fp.h \
    TPMCmd/tpm/include/prototypes/Load_fp.h \
    TPMCmd/tpm/include/prototypes/Locality_fp.h \
    TPMCmd/tpm/include/prototypes/MakeCredential_fp.h \
    TPMCmd/tpm/include/prototypes/Manufacture_fp.h \
    TPMCmd/tpm/include/prototypes/Marshal_fp.h \
    TPMCmd/tpm/include/prototypes/MathOnByteBuffers_fp.h \
    TPMCmd/tpm/include/prototypes/Memory_fp.h \
    TPMCmd/tpm/include/prototypes/MsBnMalloc_fp.h \
    TPMCmd/tpm/include/prototypes/NV_Certify_fp.h \
    TPMCmd/tpm/include/prototypes/NV_ChangeAuth_fp.h \
    TPMCmd/tpm/include/prototypes/NV_DefineSpace_fp.h \
    TPMCmd/tpm/include/prototypes/NvDynamic_fp.h \
    TPMCmd/tpm/include/prototypes/NV_Extend_fp.h \
    TPMCmd/tpm/include/prototypes/NV_GlobalWriteLock_fp.h \
    TPMCmd/tpm/include/prototypes/NV_Increment_fp.h \
    TPMCmd/tpm/include/prototypes/NV_Read_fp.h \
    TPMCmd/tpm/include/prototypes/NV_ReadLock_fp.h \
    TPMCmd/tpm/include/prototypes/NV_ReadPublic_fp.h \
    TPMCmd/tpm/include/prototypes/NvReserved_fp.h \
    TPMCmd/tpm/include/prototypes/NV_SetBits_fp.h \
    TPMCmd/tpm/include/prototypes/NV_spt_fp.h \
    TPMCmd/tpm/include/prototypes/NV_UndefineSpace_fp.h \
    TPMCmd/tpm/include/prototypes/NV_UndefineSpaceSpecial_fp.h \
    TPMCmd/tpm/include/prototypes/NV_Write_fp.h \
    TPMCmd/tpm/include/prototypes/NV_WriteLock_fp.h \
    TPMCmd/tpm/include/prototypes/ObjectChangeAuth_fp.h \
    TPMCmd/tpm/include/prototypes/Object_fp.h \
    TPMCmd/tpm/include/prototypes/Object_spt_fp.h \
    TPMCmd/tpm/include/prototypes/PCR_Allocate_fp.h \
    TPMCmd/tpm/include/prototypes/PCR_Event_fp.h \
    TPMCmd/tpm/include/prototypes/PCR_Extend_fp.h \
    TPMCmd/tpm/include/prototypes/PCR_fp.h \
    TPMCmd/tpm/include/prototypes/PCR_Read_fp.h \
    TPMCmd/tpm/include/prototypes/PCR_Reset_fp.h \
    TPMCmd/tpm/include/prototypes/PCR_SetAuthPolicy_fp.h \
    TPMCmd/tpm/include/prototypes/PCR_SetAuthValue_fp.h \
    TPMCmd/tpm/include/prototypes/PolicyAuthorize_fp.h \
    TPMCmd/tpm/include/prototypes/PolicyAuthorizeNV_fp.h \
    TPMCmd/tpm/include/prototypes/PolicyAuthValue_fp.h \
    TPMCmd/tpm/include/prototypes/PolicyCommandCode_fp.h \
    TPMCmd/tpm/include/prototypes/PolicyCounterTimer_fp.h \
    TPMCmd/tpm/include/prototypes/PolicyCpHash_fp.h \
    TPMCmd/tpm/include/prototypes/PolicyDuplicationSelect_fp.h \
    TPMCmd/tpm/include/prototypes/PolicyGetDigest_fp.h \
    TPMCmd/tpm/include/prototypes/PolicyLocality_fp.h \
    TPMCmd/tpm/include/prototypes/PolicyNameHash_fp.h \
    TPMCmd/tpm/include/prototypes/PolicyNV_fp.h \
    TPMCmd/tpm/include/prototypes/PolicyNvWritten_fp.h \
    TPMCmd/tpm/include/prototypes/PolicyOR_fp.h \
    TPMCmd/tpm/include/prototypes/PolicyPassword_fp.h \
    TPMCmd/tpm/include/prototypes/PolicyPCR_fp.h \
    TPMCmd/tpm/include/prototypes/PolicyPhysicalPresence_fp.h \
    TPMCmd/tpm/include/prototypes/PolicyRestart_fp.h \
    TPMCmd/tpm/include/prototypes/PolicySecret_fp.h \
    TPMCmd/tpm/include/prototypes/PolicySigned_fp.h \
    TPMCmd/tpm/include/prototypes/Policy_spt_fp.h \
    TPMCmd/tpm/include/prototypes/PolicyTemplate_fp.h \
    TPMCmd/tpm/include/prototypes/PolicyTicket_fp.h \
    TPMCmd/tpm/include/prototypes/Power_fp.h \
    TPMCmd/tpm/include/prototypes/PP_Commands_fp.h \
    TPMCmd/tpm/include/prototypes/PP_fp.h \
    TPMCmd/tpm/include/prototypes/PrimeData_fp.h \
    TPMCmd/tpm/include/prototypes/PropertyCap_fp.h \
    TPMCmd/tpm/include/prototypes/Quote_fp.h \
    TPMCmd/tpm/include/prototypes/ReadClock_fp.h \
    TPMCmd/tpm/include/prototypes/ReadPublic_fp.h \
    TPMCmd/tpm/include/prototypes/ResponseCodeProcessing_fp.h \
    TPMCmd/tpm/include/prototypes/Response_fp.h \
    TPMCmd/tpm/include/prototypes/Rewrap_fp.h \
    TPMCmd/tpm/include/prototypes/RSA_Decrypt_fp.h \
    TPMCmd/tpm/include/prototypes/RSA_Encrypt_fp.h \
    TPMCmd/tpm/include/prototypes/RsaKeyCache_fp.h \
    TPMCmd/tpm/include/prototypes/SelfTest_fp.h \
    TPMCmd/tpm/include/prototypes/SequenceComplete_fp.h \
    TPMCmd/tpm/include/prototypes/SequenceUpdate_fp.h \
    TPMCmd/tpm/include/prototypes/Session_fp.h \
    TPMCmd/tpm/include/prototypes/SessionProcess_fp.h \
    TPMCmd/tpm/include/prototypes/SetAlgorithmSet_fp.h \
    TPMCmd/tpm/include/prototypes/SetCommandCodeAuditStatus_fp.h \
    TPMCmd/tpm/include/prototypes/SetPrimaryPolicy_fp.h \
    TPMCmd/tpm/include/prototypes/Shutdown_fp.h \
    TPMCmd/tpm/include/prototypes/Sign_fp.h \
    TPMCmd/tpm/include/prototypes/Simulator_fp.h \
    TPMCmd/tpm/include/prototypes/StartAuthSession_fp.h \
    TPMCmd/tpm/include/prototypes/Startup_fp.h \
    TPMCmd/tpm/include/prototypes/StirRandom_fp.h \
    TPMCmd/tpm/include/prototypes/TestParms_fp.h \
    TPMCmd/tpm/include/prototypes/Ticket_fp.h \
    TPMCmd/tpm/include/prototypes/Time_fp.h \
    TPMCmd/tpm/include/prototypes/TpmFail_fp.h \
    TPMCmd/tpm/include/prototypes/_TPM_Hash_Data_fp.h \
    TPMCmd/tpm/include/prototypes/_TPM_Hash_End_fp.h \
    TPMCmd/tpm/include/prototypes/_TPM_Hash_Start_fp.h \
    TPMCmd/tpm/include/prototypes/_TPM_Init_fp.h \
    TPMCmd/tpm/include/prototypes/TpmSizeChecks_fp.h \
    TPMCmd/tpm/include/prototypes/TpmToLtcDesSupport_fp.h \
    TPMCmd/tpm/include/prototypes/TpmToLtcMath_fp.h \
    TPMCmd/tpm/include/prototypes/TpmToLtcSupport_fp.h \
    TPMCmd/tpm/include/prototypes/TpmToOsslDesSupport_fp.h \
    TPMCmd/tpm/include/prototypes/TpmToOsslMath_fp.h \
    TPMCmd/tpm/include/prototypes/TpmToOsslSupport_fp.h \
    TPMCmd/tpm/include/prototypes/Unseal_fp.h \
    TPMCmd/tpm/include/prototypes/Vendor_TCG_Test_fp.h \
    TPMCmd/tpm/include/prototypes/VerifySignature_fp.h \
    TPMCmd/tpm/include/prototypes/ZGen_2Phase_fp.h \
    TPMCmd/tpm/include/RsaTestData.h \
    TPMCmd/tpm/include/SelfTest.h \
    TPMCmd/tpm/include/SupportLibraryFunctionPrototypes_fp.h \
    TPMCmd/tpm/include/swap.h \
    TPMCmd/tpm/include/SymmetricTestData.h \
    TPMCmd/tpm/include/SymmetricTest.h \
    TPMCmd/tpm/include/TPMB.h \
    TPMCmd/tpm/include/TpmBuildSwitches.h \
    TPMCmd/tpm/include/TpmError.h \
    TPMCmd/tpm/include/Tpm.h \
    TPMCmd/tpm/include/TpmTypes.h \
    TPMCmd/tpm/include/VendorString.h \
    TPMCmd/tpm/src/command/Asymmetric/ECC_Parameters.c \
    TPMCmd/tpm/src/command/Asymmetric/ECDH_KeyGen.c \
    TPMCmd/tpm/src/command/Asymmetric/ECDH_ZGen.c \
    TPMCmd/tpm/src/command/Asymmetric/EC_Ephemeral.c \
    TPMCmd/tpm/src/command/Asymmetric/RSA_Decrypt.c \
    TPMCmd/tpm/src/command/Asymmetric/RSA_Encrypt.c \
    TPMCmd/tpm/src/command/Asymmetric/ZGen_2Phase.c \
    TPMCmd/tpm/src/command/Attestation/Attest_spt.c \
    TPMCmd/tpm/src/command/Attestation/Certify.c \
    TPMCmd/tpm/src/command/Attestation/CertifyCreation.c \
    TPMCmd/tpm/src/command/Attestation/GetCommandAuditDigest.c \
    TPMCmd/tpm/src/command/Attestation/GetSessionAuditDigest.c \
    TPMCmd/tpm/src/command/Attestation/GetTime.c \
    TPMCmd/tpm/src/command/Attestation/Quote.c \
    TPMCmd/tpm/src/command/Capability/GetCapability.c \
    TPMCmd/tpm/src/command/Capability/TestParms.c \
    TPMCmd/tpm/src/command/ClockTimer/ClockRateAdjust.c \
    TPMCmd/tpm/src/command/ClockTimer/ClockSet.c \
    TPMCmd/tpm/src/command/ClockTimer/ReadClock.c \
    TPMCmd/tpm/src/command/CommandAudit/SetCommandCodeAuditStatus.c \
    TPMCmd/tpm/src/command/Context/ContextLoad.c \
    TPMCmd/tpm/src/command/Context/ContextSave.c \
    TPMCmd/tpm/src/command/Context/Context_spt.c \
    TPMCmd/tpm/src/command/Context/EvictControl.c \
    TPMCmd/tpm/src/command/Context/FlushContext.c \
    TPMCmd/tpm/src/command/DA/DictionaryAttackLockReset.c \
    TPMCmd/tpm/src/command/DA/DictionaryAttackParameters.c \
    TPMCmd/tpm/src/command/Duplication/Duplicate.c \
    TPMCmd/tpm/src/command/Duplication/Import.c \
    TPMCmd/tpm/src/command/Duplication/Rewrap.c \
    TPMCmd/tpm/src/command/EA/PolicyAuthorize.c \
    TPMCmd/tpm/src/command/EA/PolicyAuthorizeNV.c \
    TPMCmd/tpm/src/command/EA/PolicyAuthValue.c \
    TPMCmd/tpm/src/command/EA/PolicyCommandCode.c \
    TPMCmd/tpm/src/command/EA/PolicyCounterTimer.c \
    TPMCmd/tpm/src/command/EA/PolicyCpHash.c \
    TPMCmd/tpm/src/command/EA/PolicyDuplicationSelect.c \
    TPMCmd/tpm/src/command/EA/PolicyGetDigest.c \
    TPMCmd/tpm/src/command/EA/PolicyLocality.c \
    TPMCmd/tpm/src/command/EA/PolicyNameHash.c \
    TPMCmd/tpm/src/command/EA/PolicyNV.c \
    TPMCmd/tpm/src/command/EA/PolicyNvWritten.c \
    TPMCmd/tpm/src/command/EA/PolicyOR.c \
    TPMCmd/tpm/src/command/EA/PolicyPassword.c \
    TPMCmd/tpm/src/command/EA/PolicyPCR.c \
    TPMCmd/tpm/src/command/EA/PolicyPhysicalPresence.c \
    TPMCmd/tpm/src/command/EA/PolicySecret.c \
    TPMCmd/tpm/src/command/EA/PolicySigned.c \
    TPMCmd/tpm/src/command/EA/Policy_spt.c \
    TPMCmd/tpm/src/command/EA/PolicyTemplate.c \
    TPMCmd/tpm/src/command/EA/PolicyTicket.c \
    TPMCmd/tpm/src/command/Ecdaa/Commit.c \
    TPMCmd/tpm/src/command/FieldUpgrade/FieldUpgradeData.c \
    TPMCmd/tpm/src/command/FieldUpgrade/FieldUpgradeStart.c \
    TPMCmd/tpm/src/command/FieldUpgrade/FirmwareRead.c \
    TPMCmd/tpm/src/command/HashHMAC/EventSequenceComplete.c \
    TPMCmd/tpm/src/command/HashHMAC/HashSequenceStart.c \
    TPMCmd/tpm/src/command/HashHMAC/HMAC_Start.c \
    TPMCmd/tpm/src/command/HashHMAC/SequenceComplete.c \
    TPMCmd/tpm/src/command/HashHMAC/SequenceUpdate.c \
    TPMCmd/tpm/src/command/Hierarchy/ChangeEPS.c \
    TPMCmd/tpm/src/command/Hierarchy/ChangePPS.c \
    TPMCmd/tpm/src/command/Hierarchy/Clear.c \
    TPMCmd/tpm/src/command/Hierarchy/ClearControl.c \
    TPMCmd/tpm/src/command/Hierarchy/CreatePrimary.c \
    TPMCmd/tpm/src/command/Hierarchy/HierarchyChangeAuth.c \
    TPMCmd/tpm/src/command/Hierarchy/HierarchyControl.c \
    TPMCmd/tpm/src/command/Hierarchy/SetPrimaryPolicy.c \
    TPMCmd/tpm/src/command/Misc/PP_Commands.c \
    TPMCmd/tpm/src/command/Misc/SetAlgorithmSet.c \
    TPMCmd/tpm/src/command/NVStorage/NV_Certify.c \
    TPMCmd/tpm/src/command/NVStorage/NV_ChangeAuth.c \
    TPMCmd/tpm/src/command/NVStorage/NV_DefineSpace.c \
    TPMCmd/tpm/src/command/NVStorage/NV_Extend.c \
    TPMCmd/tpm/src/command/NVStorage/NV_GlobalWriteLock.c \
    TPMCmd/tpm/src/command/NVStorage/NV_Increment.c \
    TPMCmd/tpm/src/command/NVStorage/NV_Read.c \
    TPMCmd/tpm/src/command/NVStorage/NV_ReadLock.c \
    TPMCmd/tpm/src/command/NVStorage/NV_ReadPublic.c \
    TPMCmd/tpm/src/command/NVStorage/NV_SetBits.c \
    TPMCmd/tpm/src/command/NVStorage/NV_spt.c \
    TPMCmd/tpm/src/command/NVStorage/NV_UndefineSpace.c \
    TPMCmd/tpm/src/command/NVStorage/NV_UndefineSpaceSpecial.c \
    TPMCmd/tpm/src/command/NVStorage/NV_Write.c \
    TPMCmd/tpm/src/command/NVStorage/NV_WriteLock.c \
    TPMCmd/tpm/src/command/Object/ActivateCredential.c \
    TPMCmd/tpm/src/command/Object/Create.c \
    TPMCmd/tpm/src/command/Object/CreateLoaded.c \
    TPMCmd/tpm/src/command/Object/Load.c \
    TPMCmd/tpm/src/command/Object/LoadExternal.c \
    TPMCmd/tpm/src/command/Object/MakeCredential.c \
    TPMCmd/tpm/src/command/Object/ObjectChangeAuth.c \
    TPMCmd/tpm/src/command/Object/Object_spt.c \
    TPMCmd/tpm/src/command/Object/ReadPublic.c \
    TPMCmd/tpm/src/command/Object/Unseal.c \
    TPMCmd/tpm/src/command/PCR/PCR_Allocate.c \
    TPMCmd/tpm/src/command/PCR/PCR_Event.c \
    TPMCmd/tpm/src/command/PCR/PCR_Extend.c \
    TPMCmd/tpm/src/command/PCR/PCR_Read.c \
    TPMCmd/tpm/src/command/PCR/PCR_Reset.c \
    TPMCmd/tpm/src/command/PCR/PCR_SetAuthPolicy.c \
    TPMCmd/tpm/src/command/PCR/PCR_SetAuthValue.c \
    TPMCmd/tpm/src/command/Random/GetRandom.c \
    TPMCmd/tpm/src/command/Random/StirRandom.c \
    TPMCmd/tpm/src/command/Session/PolicyRestart.c \
    TPMCmd/tpm/src/command/Session/StartAuthSession.c \
    TPMCmd/tpm/src/command/Signature/Sign.c \
    TPMCmd/tpm/src/command/Signature/VerifySignature.c \
    TPMCmd/tpm/src/command/Startup/Shutdown.c \
    TPMCmd/tpm/src/command/Startup/Startup.c \
    TPMCmd/tpm/src/command/Symmetric/EncryptDecrypt2.c \
    TPMCmd/tpm/src/command/Symmetric/EncryptDecrypt.c \
    TPMCmd/tpm/src/command/Symmetric/EncryptDecrypt_spt.c \
    TPMCmd/tpm/src/command/Symmetric/Hash.c \
    TPMCmd/tpm/src/command/Symmetric/HMAC.c \
    TPMCmd/tpm/src/command/Testing/GetTestResult.c \
    TPMCmd/tpm/src/command/Testing/IncrementalSelfTest.c \
    TPMCmd/tpm/src/command/Testing/SelfTest.c \
    TPMCmd/tpm/src/command/Vendor/Vendor_TCG_Test.c \
    TPMCmd/tpm/src/crypt/AlgorithmTests.c \
    TPMCmd/tpm/src/crypt/BnConvert.c \
    TPMCmd/tpm/src/crypt/BnEccData.c \
    TPMCmd/tpm/src/crypt/BnMath.c \
    TPMCmd/tpm/src/crypt/BnMemory.c \
    TPMCmd/tpm/src/crypt/CryptDes.c \
    TPMCmd/tpm/src/crypt/CryptEccKeyExchange.c \
    TPMCmd/tpm/src/crypt/CryptEccMain.c \
    TPMCmd/tpm/src/crypt/CryptEccSignature.c \
    TPMCmd/tpm/src/crypt/CryptHash.c \
    TPMCmd/tpm/src/crypt/CryptHashData.c \
    TPMCmd/tpm/src/crypt/CryptPrime.c \
    TPMCmd/tpm/src/crypt/CryptPrimeSieve.c \
    TPMCmd/tpm/src/crypt/CryptRand.c \
    TPMCmd/tpm/src/crypt/CryptRsa.c \
    TPMCmd/tpm/src/crypt/CryptSelfTest.c \
    TPMCmd/tpm/src/crypt/CryptSym.c \
    TPMCmd/tpm/src/crypt/CryptUtil.c \
    TPMCmd/tpm/src/crypt/ltc/TpmToLtcDesSupport.c \
    TPMCmd/tpm/src/crypt/ltc/TpmToLtcMath.c \
    TPMCmd/tpm/src/crypt/ltc/TpmToLtcSupport.c \
    TPMCmd/tpm/src/crypt/ossl/TpmToOsslDesSupport.c \
    TPMCmd/tpm/src/crypt/ossl/TpmToOsslMath.c \
    TPMCmd/tpm/src/crypt/ossl/TpmToOsslSupport.c \
    TPMCmd/tpm/src/crypt/PrimeData.c \
    TPMCmd/tpm/src/crypt/RsaKeyCache.c \
    TPMCmd/tpm/src/crypt/Ticket.c \
    TPMCmd/tpm/src/events/_TPM_Hash_Data.c \
    TPMCmd/tpm/src/events/_TPM_Hash_End.c \
    TPMCmd/tpm/src/events/_TPM_Hash_Start.c \
    TPMCmd/tpm/src/events/_TPM_Init.c \
    TPMCmd/tpm/src/main/CommandDispatcher.c \
    TPMCmd/tpm/src/main/ExecCommand.c \
    TPMCmd/tpm/src/main/SessionProcess.c \
    TPMCmd/tpm/src/subsystem/CommandAudit.c \
    TPMCmd/tpm/src/subsystem/DA.c \
    TPMCmd/tpm/src/subsystem/Hierarchy.c \
    TPMCmd/tpm/src/subsystem/NvDynamic.c \
    TPMCmd/tpm/src/subsystem/NvReserved.c \
    TPMCmd/tpm/src/subsystem/Object.c \
    TPMCmd/tpm/src/subsystem/PCR.c \
    TPMCmd/tpm/src/subsystem/PP.c \
    TPMCmd/tpm/src/subsystem/Session.c \
    TPMCmd/tpm/src/subsystem/Time.c \
    TPMCmd/tpm/src/support/AlgorithmCap.c \
    TPMCmd/tpm/src/support/Bits.c \
    TPMCmd/tpm/src/support/CommandCodeAttributes.c \
    TPMCmd/tpm/src/support/Entity.c \
    TPMCmd/tpm/src/support/Global.c \
    TPMCmd/tpm/src/support/Handle.c \
    TPMCmd/tpm/src/support/IoBuffers.c \
    TPMCmd/tpm/src/support/Locality.c \
    TPMCmd/tpm/src/support/Manufacture.c \
    TPMCmd/tpm/src/support/Marshal.c \
    TPMCmd/tpm/src/support/MathOnByteBuffers.c \
    TPMCmd/tpm/src/support/Memory.c \
    TPMCmd/tpm/src/support/Power.c \
    TPMCmd/tpm/src/support/PropertyCap.c \
    TPMCmd/tpm/src/support/Response.c \
    TPMCmd/tpm/src/support/ResponseCodeProcessing.c \
    TPMCmd/tpm/src/support/TpmFail.c \
    TPMCmd/tpm/src/support/TpmSizeChecks.c \
"
