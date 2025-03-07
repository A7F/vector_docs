[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADFX/Functions/CAPLfunctionA664CloseProxyPort.md)

# A664CloseProxyPort

[CAPL Functions](../../CAPLfunctions.md) » AFDX » A664CloseProxyPort

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```
long a664CloseProxyPort (WORD channel, DWORD outMsgId)
```

## Description

Method to close a specific socket port, which was generated using [a664InitProxyPort](CAPLfunctionA664InitProxyPort.md).

This call is only required, if an existing message-pair or UDP-port combination needs to be modified.

On measurement end all existing proxy-ports are closed automatically.

## Parameters

- **<channel>**: AFDX-channel (1 to 16) to which socket packets should be mapped to (sent and observed).
- **<outMsgID>**: messageID which is observed on AFDX-channel and transferred to the socket if detected.

## Return Values

- **0**: Successfully closed socket.
  - **Note**: closing a none existing socket is not an error.
- **-1**: Error: closing an existing socket failed.

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)