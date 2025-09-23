[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSetwakeupCondition.md)

**CAPL Functions** » **LIN** » **linSetwakeupCondition**

# linSetwakeupCondition

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `linSetWakeupCondition(dword numWakeupSignals); // form 1`
- `linSetWakeupCondition(dword numWakeupSignals, dword forgetWupsAfterMS); // form 2`

## Description

Determines the conditions under which the LIN hardware can be reactivated (leaves the sleep mode).

**Note:** When LIN hardware is not in master mode calling this function will have no effect.

## Parameters

- **numWakeupSignals**  
  This parameter specifies the number of wakeup signals, after that the LIN hardware is reactivated. If the value 0 is set, the LIN hardware will never leave the sleep mode.  
  Value range: 0..31  
  Default value: 1

- **forgetWupsAfterMS**  
  This parameter defines the time after that earlier wake-up signals are not any longer taken into account for the wake-up behavior.  
  Default value: 0

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

```plaintext
// configure LIN hardware to wakeup after 3 wakeup signals
linSetWakeupCondition (3);
```
