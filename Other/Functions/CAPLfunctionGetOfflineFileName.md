[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGetOfflineFileName.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » getOfflineFileName

# getOfflineFileName

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long getOfflineFileName(char[] buffer, dword bufferSize); //form 1
long getOfflineFileName(long index, char[] buffer, dword bufferSize); // form 2
```

## Description

Returns the complete path of one file of the currently used offline source files. If form 1 is used, the first file is returned, otherwise the index of the file to return is passed as parameter.

## Parameters

- **buffer**: Space for the returned string.
- **bufferSize**: Size of the buffer.
- **index**: Index of the returned offline file.

## Return Values

- **0**: If no error
- **1**: If buffer is too small
- **2**: For other errors (e.g. not in offline mode)

## Example

```c
long isActive;
char buffer[256];
long numFiles;
long i;

write("Offline source files:");
numFiles = getNumOfflineFiles();
for (i = 0; i < numFiles; ++i)
{
  getOfflineFileName(i, buffer, 256);
  write("%s", buffer);
}
```

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
