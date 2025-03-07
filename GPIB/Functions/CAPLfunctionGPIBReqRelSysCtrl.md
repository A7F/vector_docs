[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/GPIB/Functions/CAPLfunctionGPIBReqRelSysCtrl.md)

**CAPL Functions** » **GPIB** » **GPIBReqRelSysCtrl**

# GPIBReqRelSysCtrl

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long GPIBReqRelSysCtrl 
(long boardIdx, long mode);
```

## Description

Sets or deletes the permission to send interface clear (IFC) or remote enable (REN). If mode is "0," the GPIB board surrenders system control and all controller-specific commands are not allowed. If mode = "1," then controller-specific commands are allowed.

## Parameters

- **boardIdx**: GPIB Board ID
- **mode**: (0..1)

## Return Values

- [Status](../CAPLfunctionsGPIBStatus.md)
- **-1**: On error, if no GPIB driver is available

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)