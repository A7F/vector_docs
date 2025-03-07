[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINDeactivateBitInversion.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » linDeactivateBitInversion

# linDeactivateBitInversion

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long LINDeactivateBitInversion();
```

## Description

With this function it is possible to cancel a previously activated bits inversion for LIN header or response. This function is useful when after calling [linInvertHeaderBit()](CAPLfunctionLINInvertHeaderBit.md) no header occurred yet on the bus or when after calling [linInvertRespBit()](CAPLfunctionLINInvertRespBit.md) no frame occurred yet.

## Parameters

—

## Return Values

On success a value unequal to zero, otherwise zero.

## Example

Deactivate previous bit inversion

```plaintext
on key 'd'
{
   if (0==linDeactivateBitInversion())
   {
      write("CAPL: Bit inversion deactivation failure!");
   }
}
```

[linInvertHeaderBit](CAPLfunctionLINInvertHeaderBit.md) • [linInvertRespBit](CAPLfunctionLINInvertRespBit.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)