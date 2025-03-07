[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionOpenFileWrite.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » openFileWrite

# openFileWrite

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**  
Before this function can be called the write [path](../CAPLfunctionsFileSearchProcedure.md) must be set by the function [SetWritePath](CAPLfunctionSetWritePath.md). Otherwise the configuration directory will be used. A relative filename must be passed to the function.

## Function Syntax

- `dword openFileWrite (char filename[], dword mode); // form 1`
- `dword openFileWrite (char filename[], dword mode, dword fileEncoding); // form 2`

## Description

This function opens the **filename** file for the write access.

- If `mode=0`, writing can be executed in text mode; if `mode=1`, writing can be executed in binary mode. An already existing file will be overwritten.
- `mode=2` to append data at the end of the file use for text mode.
- `mode=3` to append data at the end of the file for binary mode.

## Parameters

- **filename**: filename
- **mode**: 
- **fileEncoding**: Identifier of the Microsoft code page that is used to encode the file.

## Return Values

The return value is the file handle that must be used for write operations. If an error occurs, the return value is 0.

## Example

See [File Functions](CAPLfunctionsExapmleFileFunctions.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)