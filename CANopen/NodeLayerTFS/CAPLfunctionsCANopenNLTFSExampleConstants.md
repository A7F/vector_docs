# Constants Used in the CAPL Examples

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE

## General

- const int kTestStepPassed = 1; /* to indicate a successful execution */
- const kHandleTestResultStandard = 0;
- const kHandleTestResultInverted = 1;
- const kHandleTestResultManually = 2;

## NMT State

- const int kNMTState_BootUp = 0;
- const int kNMTState_Stopped = 4;
- const int kNMTState_Operationa1 = 5;
- const int kNMTState_PreOperational = 127;

## NMT command specifier

- const int kCommandSpecifier_StartRemoteNode = 1;
- const int kCommandSpecifier_StopRemoteNode = 2;
- const int kCommandSpecifier_EnterPreOperational = 128;
- const int kCommandSpecifier_ResetNode = 129;
- const int kCommandSpecifier_ResetCommunication = 130;

## client command specifier for SDO transfer

- const int kClientCommandSpecifier_InitiateDownloadRequest = 1;
- const int kClientCommandSpecifier_DownloadSegmentRequest = 0;
- const int kClientCommandSpecifier_InitiateUploadRequest = 2;
- const int kClientCommandSpecifier_UploadSegmentRequest = 3;
- const int kClientCommandSpecifier_BlockDownload = 6;
- const int kClientCommandSpecifier_BlockUpload = 5;

## server command specifier for SDO transfer

- const int kServerCommandSpecifier_InitiateDownloadResponse = 3;
- const int kServerCommandSpecifier_DownloadSegmentRespone = 1;
- const int kServerCommandSpecifier_InitiateUploadRespone = 2;
- const int kServerCommandSpecifier_UploadSegmentRespone = 0;
- const int kServerCommandSpecifier_BlockDownload = 5;
- const int kServerCommandSpecifier_BlockUpload = 6;

## client subcommand for SDO block transfer

- const int kClientSubcommand_InitiateDownloadRequest = 0;
- const int kClientSubcommand_EndBlockDownloadRequest = 1;
- const int kClientSubcommand_InitiateUploadRequest = 0;
- const int kClientSubcommand_StartUpload = 3;
- const int kClientSubcommnad_BlockUploadResponse = 2;
- const int kClientSubcommnad_EndBlockUploadRequest = 1;

## server subcommand for SDO block transfer

- const int kServerSubcommand_InitiateDownloadReponse = 0;
- const int kServerSubcommand_BlockDownloadResponse = 2;
- const int kServerSubcommand_EndBlockDownloadResponse = 1;
- const int kServerSubcommand_InitiateUploadReponse = 0;
- const int kServerSubcommand_EndBlockUploadResponse = 1;

## continue bit for SDO block transfer

- const int kContinueBit_MoreSegments = 0;
- const int kContinueBit_NoMoreSegments = 1;

## CRC support for SDO block transfer

- const int kCRC_NoSupport = 0;
- const int kCRC_Support = 1;

## transfer type

- const int kTransfer_Normal = 0;
- const int kTransfer_Expedited = 1;

## size

- const int kSize_Indicated = 1;
- const int kSize_NotIndicated = 0;

## cotfs access type

- const int kAccessType_ReadWrite = 1;
- const int kAccessType_ReadOnly = 2;
- const int kAccessType_WriteOnly = 3;
- const int kAccessType_Constant = 4;

## error handling

- const int kErrorHandling_RunAllTests = 0;
- const int kErrorHandling_StopOnFirstFailedTest = 1;
- const int kErrorHandling_StopOnFirstPassedTest = 2;
