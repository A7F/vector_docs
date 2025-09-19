[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestEnableUpdateBit.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestEnableUpdateBit

# TestEnableUpdateBit

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This function is not available for all OEM add-ons - depends on the CANoeIL.

## Function Syntax

```
long TestEnableUpdateBit (dbSignal aSignal);
```

## Description

Re-enables the standard behavior of the update bit, after it has been disabled with [TestDisableUpdateBit](CAPLfunctionTestDisableUpdateBit.md).

This function influences a simulation node with an assigned CANoe Interaction Layer.

**Note**  
Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aSignal**: Signal that should be reset to update bit standard behavior.

## Return Values

- **0**: No error.
- **-1**: General error.

## Example

```c
// disables the update bit of signal ‘DoorStatus_UB’ for 1000 ms
TestDisableUpdateBit(DoorStatus_UB, 0);
TestWaitForTimeout(1000);
TestEnableUpdateBit(DoorStatus_UB);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
