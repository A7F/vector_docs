[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSstopsimulation.md)

**CAPL Functions** » **J1939** » **GNSS NL** » **GNSSStopSimulation**

# GNSSStopSimulation

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword GNSSStopSimulation();
```

## Description

This function stops the simulation. This does not result in waypoints that are set being deleted.

## Parameters

—

## Return Values

[error code](../CAPLfunctionsGNSSNLErrorCodesGetLastError.md)

## Example

```plaintext
GNSSStopSimulation();
```
