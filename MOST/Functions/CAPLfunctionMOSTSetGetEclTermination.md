[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTSetGetEclTermination.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostSetEclTermination, mostGetEclTermination

# mostSetEclTermination, mostGetEclTermination

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This function is only available with MOST hardware VN2640.

## Function Syntax

```plaintext
long mostSetEclTermination(long channel, long eclTermination);
long mostGetEclTermination (long channel);
```

## Description

Sets and gets the state of the termination resistor of the Electrical Control Line.

## Parameters

- **channel**  
  Channel of the connected interface.

- **eclTermination**  
  0: pull-up not active  
  1: pull-up active

## Return Values

- **mostSetEclTermination**  
  See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

- **mostGetEclTermination**  
  >=0: See **eclState** parameter  
  <0: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostSetEcl](CAPLfunctionMOSTSetGetEcl.md) • [mostSetEclGlitchFilter](CAPLfunctionMOSTSetEclGlitchFilter.md) • [mostConfigureEclSequence](CAPLfunctionMOSTConfigureEclSequence.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)