[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGetAbsFilePath.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » getAbsFilePath

# getAbsFilePath

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**  
This function is not available in case of a [distributed environment](../CAPLfunctionsFileSearchProcedure.md).

## Function Syntax

```
long getAbsFilePath(char relPath[], char absPath[], long absPathLen);
```

## Description

Gets the absolute path of a file. As parameter the file should be defined with the relative path to the current configuration.

## Parameters

- **relPath**: A path (with or without a filename) defined relative to the current configuration. If this parameter is empty, then the full path of the current configuration will simply be returned.
- **absPath**: Buffer to which the full path name should be copied.
- **absPathLen**: Size of the buffer [in bytes] for the full path name.

## Return Values

On success this function returns length of the full path name, otherwise -1.

## Example

```c
on key 'x'
{
   char absPath[256];
   getAbsFilePath("Nodes\\Test.can", absPath, 256);
   write ("absPath: %s ", absPath);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
