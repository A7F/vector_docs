[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimSetCRL.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_TIMSetCRL

# Iso11783IL_TIMSetCRL

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_TIMSetCRL(byte crlType, char crlFilePath[]); // form 1
long Iso11783IL_TIMSetCRL(dbNode participant, byte crlType, char crlFilePath[]); // form 2
```

## Description

Loads a **Certificate Revocation List** file which is used for TIM authentication. If there is already a loaded certificate file for a certificate type these file is overwritten.

## Parameters

- **crlType**: Type if CRL.
  - **0**: Certificate Revocation List for Testlab, Manufacturer, manufacturer series, TIM client and TIM server certificates.
  - **1**: Certificate Revocation List for the CRL signing CA certificates.

- **crlFilePath**: Path of a CRL file (DER file format). Path has to be absolute or relative relating to the folder of the CANoe configuration.

- **participant**: TIM participant (TIM server or TIM client).

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—
