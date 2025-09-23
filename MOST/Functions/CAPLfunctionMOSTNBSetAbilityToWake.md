[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTNBSetAbilityToWake.md)

**CAPL Functions** » **MOST** » **mostNBSetAbilityToWake**

# mostNBSetAbilityToWake

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
The property "AbilityToWake" is renamed in NetBlock version 2V5 to "PermissionToWake". The behavior remains the same.

## Function Syntax

`mostNBSetAbilityToWake(long wakestatus);`

## Description

Sets the AbilityToWake flags in NetBlock.

If this flag is set to "Off", the connected MOST interface must not wake-up the ring.

## Parameters

- **wakestatus**  
  - 0: Off
  - 1: On
  - 2: Critical

## Return Values

- **\<0**  
  See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—
