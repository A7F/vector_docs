[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANstress/Functions/CAPLfunctionCANstressCreateServer.md)

[CAPL Functions](../../CAPLfunctions.md) » [CANstresss](../CAPLfunctionsCANstressOverview.md) » CANstressCreateServer

# CANstressCreateServer

**Valid for**: CANoe DE

**Note**: This function must be called before all other CANstress CAPL functions!

## Function Syntax

```
long CANstressCreateServer();
```

## Description

Starts the CANstress software and establishes a connection via the COM interface to this COM server. If no registered CANstress COM server is found, the ongoing measurement is stopped.

## Parameters

—

## Return Values

- **0**: If successful.
- **-1**: In case of error.

## Example

—

•  Technical References are only available in English

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)