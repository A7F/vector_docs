[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AVBIL/Functions/CAPLfunctionAvbILControlResume.md)

**CAPL Functions** » **Ethernet** » **AVB IL** » **AvbILControlResume**

# AvbILControlResume

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword AvbILControlResume();
```

## Description

Resumes AVB/TSN automatic message sending behavior after a previous suspension by [AvbILControlWait](CAPLfunctionAvbILControlWait.md). Previously opened Talkers and Listeners do not have to be opened again.

## Parameters

—

## Return Values

- **0**: The function was successfully executed.
- **>0**: [Error code](../CAPLfunctionsAVBILErrorCode.md)

## Example

—

[See Also](javascript:void(0);)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)