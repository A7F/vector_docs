[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionSetWritePath.md)

**CAPL Functions** » **General** » **Function Overview** » **setWritePath**

# setWritePath

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**  
This function is not available in case of a [distributed environment](../CAPLfunctionsFileSearchProcedure.md).  
After drive letters and also between folders you have to enter two "\\" e.g. `setWritePath("E:\\testconfiguration\\exercise")`.

## Function Syntax

```plaintext
void setWritePath (char relativeOrAbsolutePath[]);
```

## Description

This function sets the write [path](../CAPLfunctionsFileSearchProcedure.md) for the functions [openFileWrite](CAPLfunctionOpenFileWrite.md), [writeProfileString](CAPLfunctionWriteProFileString.md), [writeProfileInt](CAPLfunctionWriteProFileInt.md), [writeProfileFloat](CAPLfunctionWriteProFileFloat.md). The path can be given as absolute or relative to the currently active configuration.

## Parameters

The file path as a string.

## Return Values

—

## Example

`SetWritePath("C:\\TEMP")` – after the drive letter (e.g. "C:") you have to enter two backslashes "\\"!

[setFilePath](CAPLfunctionSetFilePath.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
