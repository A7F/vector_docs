[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939NodeLayer/Functions/CAPLfunctionJ1939ECUGoOffline.md)

## J1939ECUGoOffline

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 NL](../CAPLfunctionsJ1939NLOverview.md) » J1939ECUGoOffline

### Function Syntax

```
dword J1939ECUGoOffline( dword ecuHandle );
```

### Description

The function switches the state of the node to offline. It does not send a cannot claim address parameter group.

After calling this function the node cannot send any parameter groups, but it is responding to requests for address claim.

Use the function [J1939ECUGoOnline](CAPLfunctionJ1939ECUGoOnline.md) to start the node again.

### Parameters

- **ecuHandle**: ECU handle

### Return Values

0 on success or [error code](../CAPLfunctionsJ1939NLErrorCodes.md)

### Example

```c
J1939ECUGoOffline(ecuHdl);
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)