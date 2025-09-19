[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783OPChangeSoftKeyMask.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783OPChangeSoftKeyMask

# Iso11783OPChangeSoftKeyMask

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPChangeSoftKeyMask( dword ecuHandle, 
 dword maskID, dword softKeyMaskID );
```

## Description

The function changes the soft key mask of a data mask. A **Change Soft Key Mask** command is sent to the Virtual Terminal.

## Parameters

- **ecuHandle**: Handle of the ECU (must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md))
- **maskID**: Object ID of the data mask
- **softkeyMaskID**: Object ID of the data mask

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
Iso11783OPChangeSoftKeyMask( handle, 1000, 1050 );
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
