[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGetNumOfflineFiles.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » getNumOfflineFiles

# getNumOfflineFiles

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long getNumOfflineFiles();
```

## Description

Returns the number of configured offline source files.

## Parameters

—

## Return Values

- **-1**: If error (e.g., not in offline mode)
- Number of configured offline source files if no error.

## Example

```plaintext
long numFiles;

numFiles = getNumOfflineFiles();
write("Number of configured offline source files: %d", numFiles);
```

•  Technical References are only available in English

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)