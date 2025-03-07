[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForUserFileSync.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestWaitForUserFileSync

# TestWaitForUserFileSync

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long TestWaitForUserFileSync(char aFileName[], long isDirectionClientToServer);
```

## Description

This function can be used to start synchronization of [user files](../../../CANoeCANalyzer/Ribbon/File/Options/Extensions/ExtensionsUserFiles.md) between client and server system in a distributed environment. Once the synchronization has been started successfully the system waits until the file is synchronized.

The function is not allowed in [standalone mode](../../../CANoeCANalyzer/RTSetup/StandaloneMode/StandaloneModeConcept.md). Errors are reported as **error in test system** or **fail** in case of 2-valued verdict concept.

## Parameters

- **aFileName**: The name of the user file to be synchronized (path component is ignored).
- **isDirectionClientToServer**: If this parameter is set to true (≠0) the file is synchronized from the client (e.g. CANoe) to the server system.

## Return Values

- **1**: The user file was successfully synchronized.
- **-1**: General error.
- **-2**: The specified user file is not registered.
- **-3**: The user file could not be found.
- **-4**: Error while reading the source file.
- **-5**: Error while writing the destination file.
- **-6**: This function is not supported in standalone mode.
- **-7**: The file size exceeds the limit for on-line synchronization.

## Example

```c
long ret;
TestStepBegin("tc1", "sync");
ret = TestWaitForUserFileSync("UserFileCAPL.TXT", 1);
if (ret != 1) {
   TestStepFail("Transmit of \"UserFileCAPL.TXT\" from client to server failed.");
   TestCaseFail();
} else {
   TestStepPass("Synchronization succeeded.");
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)