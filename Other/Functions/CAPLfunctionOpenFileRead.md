[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionOpenFileRead.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » openFileRead

# openFileRead

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**  
A relative filename must be passed to this function. The absolute filename is determined by means of a [search procedure](../CAPLfunctionsFileSearchProcedure.md). First a search is made to determine whether the given file is located in a directory of the databases. If the desired file is not found the active configuration directory is used.

## Function Syntax

- `dword openFileRead (char filename[], dword mode); // form 1`
- `dword openFileRead (char filename[], dword mode, dword fileEncoding); // form 2`

## Description

This function opens the **filename** file for the read access.

If `mode=0` the file is opened in text mode;  
if `mode=1` the file is opened in binary mode.

## Parameters

- **filename**: filename
- **mode**: 
- **fileEncoding**: Identifier of the Microsoft code page that is used to encode the file.

## Return Values

The return value is the file handle that must be used for read operations.

If an error occurs, the return value is 0.

## Example

See [File Functions](CAPLfunctionsExapmleFileFunctions.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)