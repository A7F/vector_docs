[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILOnAddressViolation.md)

**CAPL Functions** » **ISO11783** » **Virtual Terminal Interaction Layer (VT IL)** » **VTIL_OnAddressViolation**

# VTIL_OnAddressViolation (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long VTIL_OnAddressViolation( pg * txPG );
```

## Description

This callback function is called from the IL if address violation detection is enabled ([VTIL_EnableAddressViolationDetection](CAPLfunctionIso11783VTILEnableAddressViolationDetection.md)) and if the Iso11783 IL receives the parameter group with the source address of the simulated node that was not sent by the simulated node itself.

If the callback returns 1 then the default behavior is performed: the simulated node sends an Address Claimed message and starts the cyclic sending of message DM1 with SPN=2000+nodeAddress, FMI=31 and OC=1.

If the callback returns 0 then the simulated node ignores the address violation.

## Parameters

- **rxPG**: Message which has caused the address violation.

## Return Values

- **0**: simulated node ignores the address violation.
- **1**: simulated node performs the default behavior.

## Example

—
