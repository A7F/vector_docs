[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimSetPrivateKey.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » **Iso11783IL_TIMSetPrivateKey**

# Iso11783IL_TIMSetPrivateKey

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_TIMSetPrivateKey(char privateKeyFilePath[]); // form 1
long Iso11783IL_TIMSetPrivateKey(dbNode participant, char privateKeyFilePath[]); // form 2
```

## Description

Loads an ECC private key file which is used for TIM authentication. If there is already a private key then it is overwritten.

## Parameters

- **privateKeyFilePath**: Path of a private key file which contains a hexadecimal representation of the private key. Path has to be absolute or relative relating to the folder of the CANoe configuration.
- **participant**: TIM participant (TIM server or TIM client).

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
