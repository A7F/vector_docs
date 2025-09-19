[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTSetGetEcl.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostSetEcl, mostGetEcl

# mostSetEcl, mostGetEcl

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This function is only available with MOST hardware VN2640.

## Function Syntax

```
long mostSetEcl(long channel, long eclState);
long mostGetEcl(long channel);
```

## Description

`mostSetEcl` switches the Electrical Control Line which can be used for wake-up and diagnosis purposes.

`mostGetEcl` returns the current state of the Electrical Control Line.

## Parameters

- **channel**: Channel of the connected interface.
- **eclState**:
  - 0: low
  - 1: high

## Return Values

- **mostSetEcl**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)
- **mostGetEcl**:
  - >=0: See **eclState** parameter
  - <0: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[OnMostEcl](../EventProcedures/CAPLfunctionOnMOSTEcl.md) • [mostSetEclTermination](CAPLfunctionMOSTSetGetEclTermination.md) • [mostWakeup](CAPLfunctionMOSTWakeup.md) • [mostGenerateEclSequence](CAPLfunctionMOSTGenerateEclSequence.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
