[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSendAsSporadic.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linSendAsSporadic

# linSendAsSporadic

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```plaintext
long linSendAsSporadic (long frameID);
```

## Description

This function can be used to configure an associated frame as being ready for transmission. At the next time slot, corresponding to its sporadic frame, the associated frame will be sent once.

**Note**: If LIN hardware is not in Master mode or there is no schedule table with corresponding sporadic frame defined then calling this function will have no effect.

## Parameters

- **frameID**: Identifier of the associated LIN frame to be transmitted in the next time slot of a corresponding sporadic frame.  
  Value range: 0..59, 62

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

—
