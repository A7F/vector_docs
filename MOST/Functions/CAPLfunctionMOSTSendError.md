[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTSendError.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » mostSendError

# mostSendError

**Valid for**: CANoe DE

## Function Syntax

- `mostSendError_Code (mostAmsMessage * msgcmd, byte code);` // form 1  
  (Suitable for error codes: 0x01, 0x02, 0x03, 0x05, 0x0B, 0x40, 0x41, 0x42, 0x43)

- `mostSendError_CodeByte (mostAmsMessage * msgcmd, byte code, byte byte1);` // form 2  
  (Suitable for error codes: 0x04, 0x0C, 0x20, 0x06, 0x07)

- `mostSendError_CodeByteByte(mostAmsMessage * msgcmd, byte code, byte byte1, byte byte2);` // form 3  
  (Suitable for error codes: 0x06, 0x07)

- `mostSendError_CodeByteWord(mostAmsMessage * msgcmd, byte code, byte byte1, word word1);` // form 4  
  (Suitable for error codes: 0x06, 0x07)

- `void SendError_CodeBytes(mostAMSMessage * msgcmd, byte code, byte data[], long datalen);` // form 5  
  (Suitable for error codes: 0x06, 0x07)

## Description

Generates and sends an error message directly based on a received command message. The various signatures make it easy to transfer the most common error codes with their ancillary information. Any wildcard InstId in the command message is transferred to a concrete value in the error message with the help of the device’s Local FBlock list.

## Parameters

- **msgcmd**: Received command message to be responded to
- **code**: Error Code (see MOST specification)
- **byte1**: First ancillary information as byte
- **byte2**: Second ancillary information as byte
- **word1**: Second ancillary information as word
- **data**: Ancillary information as byte array
- **datalen**: Number of valid bytes in the array with the ancillary information

## Return Values

—

## Example

—

[on mostAMSMessage](../EventProcedures/CAPLfunctionOnMOSTAMSMessage.md) • [output(mostAMSMessage * msg)](CAPLfunctionMOSToutput.md) • [mostPrepareReport](CAPLfunctionMOSTPrepareReport.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)