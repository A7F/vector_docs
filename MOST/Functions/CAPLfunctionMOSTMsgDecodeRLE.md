[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTMsgDecodeRLE.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » mostMsgDecodeRLE

# mostMsgDecodeRLE

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long mostMsgDecodeRLE(mostAmsMessage * msg, long fktIds[], long buffersize);
```

## Description

`mostMsgDecodeRLE()` decodes the data area of a message and saves the function IDs in a list. Run Length Encoding in accordance with MOST Specification 2.4 Para. 2.3.9 is used. This function is suitable for evaluating messages of the FBlock.FktIds.Status type.

## Parameters

- **msg**: Message
- **fktIds[]**: Destination buffer
- **buffersize**: Size of the destination buffer

## Return Values

- **>=0**: Number of valid function IDs in fktIds[]
- **<0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostMsgEncodeRLE](CAPLfunctionMOSTMsgEncodeRLE.md) • [mostMsgSet](CAPLfunctionMOSTMsgSet.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)