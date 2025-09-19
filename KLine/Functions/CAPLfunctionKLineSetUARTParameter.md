[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/KLine/Functions/CAPLfunctionKLineSetUARTParameter.md)

**CAPL Functions** » [K-Line](../CAPLfunctionsKLineOverview.md) » KLine_SetUARTParameter

# KLine_SetUARTParameter

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```plaintext
long KLine_SetUARTParameter(dword dataBits, dword parity, dword stopBits);
```

## Description

Configures the way bytes are sent on K-Line, by setting the parameters the UART (universal asynchronous receiver/transmitter) uses.

## Parameters

- **dataBits**: Number of bits a byte consists of. Possible values: 7, 8, 9. **Note:** 7 bits in a byte will not allow standard K-Line communication.
- **parity**: If a parity bit is used to indicate the number of bits set in the byte. **1** means _odd_ and **2** _even_ parity. A value of 0 indicates that no parity bit is used.
- **stopBits**: The number of stop bits that indicate the end of a byte. 1 or 2 is possible.

## Return Values

On success 0, otherwise [error code](../../Diagnostics/CAPLfunctionsDiagnosticsErrorCode.md).

## Example

```plaintext
KLine_CreateECURepresentation( gMsgChannel);
KLine_SetUARTParameter( 9, 1, 2); // 9 data bits, odd parity, 2 stop bits => 13 bit/byte (including start bit)
```

[KLine_SetBaudrate](CAPLfunctionKLineSetBaudrate.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
