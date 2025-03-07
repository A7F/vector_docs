[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/Functions/CAPLfunctionMediaReleaseDemultiplexer.md)

# MediaReleaseDemultiplexer

[CAPL Functions](../../CAPLfunctions.md) » [Media API](../CAPLfunctionsMediaOverview.md) » MediaReleaseDemultiplexer

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long MediaReleaseDemultiplexer(dword demultiplexerHandle);
```

## Description

Releases a demultiplexer.

## Parameters

- **demultiplexerHandle**: The multiplexer handle returned previously by a call to [MediaCreateDemultiplexer](CAPLfunctionMediaCreateDemultiplexer.md).

## Return Values

- **0**: The function succeeded.
- **≠0**: [Error code](../CAPLfunctionsMediaErrorCodes.md).

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)