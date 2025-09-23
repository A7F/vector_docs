[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSetBusIdleTimeout.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » linSetBusIdleTimeout

# linSetBusIdleTimeout

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword linSetBusIdleTimeout(dword timeout);
```

## Description

This function sets a new bus idle timeout. Depending on the protocol version, the timeout will be specified in bit times (LIN 1.x and Cooling) or in milliseconds (all others).

## Parameters

- **timeout**  
  The timeout in bit times (LIN 1.x and Cooling) or milliseconds (all other LIN protocols).  
  Value range: 1 - 32767

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

—

[linGetBusIdleTimeout](CAPLfunctionLINGetBusIdleTimeout.md)
