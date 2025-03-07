[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADAS/Functions/CAPLfunctionADASSetOutputData.md)

# ADASSetOutputData

[CAPL Functions](../../CAPLfunctions.md) » [ADAS](../CAPLfunctionsADASOverview.md) » ADASSetOutputData

Valid for:  CANoe DE

## Function Syntax

```
long ADASSetOutputData( byte data[], dword dataSize, char sysvarPrefix[] );
```

## Description

This method is used to set a byte array as ADAS output. The System Variables with the specified prefix are set to the internal memory address (lo/hi/size) of the byte array. These System Variables can then be used by an external model (e.g. Simulink Model, FMU, etc.) to retrieve the byte array from memory. If no System Variables with the specified prefix were found, this function call will have no effects.

## Parameters

- **data**: The byte array to be set as output data.
- **dataSize**: The size of the byte array.
- **sysvarPrefix**: The prefix path of the system variables to be set.

## Return Values

- **0**: Success
- **1**: Failure

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)