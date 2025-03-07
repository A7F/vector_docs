[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/KLine/Functions/CAPLfunctionKLineSetHeaderFormat.md)

[CAPL Functions](../../CAPLfunctions.md) » [K-Line](../CAPLfunctionsKLineOverview.md) » KLine_SetHeaderFormat

# KLine_SetHeaderFormat

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long KLine_SetHeaderFormat(long useAddresses, long forceLengthByte)
```

## Description

Configures the used header format.

## Parameters

- **useAddresses**  
  0: Address bytes are not used.  
  1: Address bytes are used.

- **forceLengthByte**  
  0: No Length byte will be sent.  
  1: Length byte will always be sent.  
  2: Length byte will be sent for frames greater than 63 bytes.

## Return Values

On success 0, otherwise a value less than 0.

## Example

```plaintext
KLine_SetHeaderFormat(0, 0); // A one byte header will be sent.
KLine_SetHeaderFormat(0, 1); // A two byte header will be sent.
KLine_SetHeaderFormat(1, 0); // A three byte header will be sent.
KLine_SetHeaderFormat(1, 1); // A four byte header will be sent.
```

[KLine_UseDefaultHeader](CAPLfunctionKLineUseDefaultHeader.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)