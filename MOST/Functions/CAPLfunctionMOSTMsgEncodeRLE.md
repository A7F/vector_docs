[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTMsgEncodeRLE.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostMsgEncodeRLE

# mostMsgEncodeRLE

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long mostMsgEncodeRLE(mostAmsMessage * msg, long fktIds[], long size);
```

## Description

`mostMsgEncodeRLE()` encodes a list of function IDs and saves it in the data area of a message. Run Length Encoding in accordance with MOST Specification 2.4 Para. 2.3.9 is used. This function is suitable for compiling messages of the FBlock.FktIds.Status type.

## Parameters

- **msg**: Message, which is to have data input into it.
- **fktIds[]**: List of function IDs (can be unsorted).
- **size**: Number of function IDs in fktIds[].

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostMsgDecodeRLE](CAPLfunctionMOSTMsgDecodeRLE.md) • [mostMsgSet](CAPLfunctionMOSTMsgSet.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
