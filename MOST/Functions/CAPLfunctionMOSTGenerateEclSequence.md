[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTGenerateEclSequence.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostGenerateEclSequence

# mostGenerateEclSequence

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This function is only available with MOST hardware VN2640.

## Function Syntax

```plaintext
long mostGenerateEclSequence (long channel, long startstop);
```

## Description

Starts the generation of the signal sequence on the ECL which was prepared by [mostConfigureEclSequence](CAPLfunctionMOSTConfigureEclSequence.md). Dominant levels will be set actively whereas during recessive phases the generator is passive and other devices connected to the ECL may pull the line to dominant level.

## Parameters

- **channel**: Channel of the connected interface.
- **startstop**:
  - 0: stops the generation of the sequence
  - 1: starts the generation of the sequence

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

See [mostConfigureEclSequence](CAPLfunctionMOSTConfigureEclSequence.md)

[mostConfigureEclSequence](CAPLfunctionMOSTConfigureEclSequence.md) • [mostSetEcl](CAPLfunctionMOSTSetGetEcl.md) • [OnMostEcl](../EventProcedures/CAPLfunctionOnMOSTEcl.md) • [mostSetEclTermination](CAPLfunctionMOSTSetGetEclTermination.md) • [OnMostEclSequence](../EventProcedures/CAPLfunctionOnMOSTEclSequence.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
