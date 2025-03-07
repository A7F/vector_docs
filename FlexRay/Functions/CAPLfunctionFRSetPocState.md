[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/FlexRay/Functions/CAPLfunctionFRSetPocState.md)

[CAPL Functions](../../CAPLfunctions.md) » [FlexRay](../CAPLfunctionsFlexrayOverview.md) » frSetPOCState

# frSetPOCState

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
The function is supported by VN interfaces only!

## Function Syntax

```
long frSetPOCState( long channel, long ccNumber, long pocState );
```

## Description

This function puts the FlexRay **C**ommunication **C**ontroller (CC) into the desired **P**rotocol **O**peration **M**ode (POC state). The function is non-blocking. That means, the function will return before the CC has reached the desired POC-state.

All E-Ray POC-state changes can be monitored with the status- or POC-state-events. A status event is generated as soon as the second CC has reached the desired POC-state.

## Parameters

- **Channel**: FlexRay channel (cluster number).
- **ccNumber**: 
  - 1: E-Ray
  - 2: Second Startup Controller/Coldstart helper (Fujitsu)
- **pocState**: Desired POC state:
  - **0**: wakeup
  - **1**: normal active
  - **2**: halt
  - **3**: ready

## Return Values

- **0**: Error (wrong parameter, or the POC state cannot be reached)

## Example

—

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)