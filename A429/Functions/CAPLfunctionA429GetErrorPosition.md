# a429GetErrorPosition

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```plaintext
long a429GetErrorPosition( a429worderror myA429word );
```

## Description

For every [Rx error](../CAPLfunctionsA429Selectors.md) an error position is provided. You may access this information with the operator **this** in an [on a429Worderror](../EventProcedures/CAPLfunctionA429OnA429WordError.md) handler.

## Parameters

- **myA429word**: ARINC word in `on a429Worderror` handler

## Return Values

- **-1**: there is no error position available
- **0..255**: error position in the ARINC word (in case of gap violation the position in the gap area is given)

## Example

—
