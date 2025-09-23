[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/KLine/Functions/CAPLfunctionKLineInit5BaudEcuParams.md)

**CAPL Functions** » **K-Line** » **KLine_Init5BaudEcuParams**

# KLine_Init5BaudEcuParams

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Function Syntax

```plaintext
long KLine_Init5BaudEcuParams(dword 5BaudAddress, dword rate_10thBd, dword W1_us, dword W2_us, dword W3_us, dword W4_us, dword W4Min_us, dword W4Max_us, dword addressNot);
```

## Description

Initialize K-Line channel for reception of the 5 baud pattern.

**Note**: Must be called in **on prestart** handler after [KLine_CreateECURepresentation](CAPLfunctionKLineCreateECURepresentation.md).

## Parameters

- **5BaudAddress**: The 5 Baud address to accept on the active channel.
- **rate_10thBd**: Rate of the address in 1/10 of baud, i.e. a value of 50 should be used here.
- **W1_us**, **W2_us**, **W3_us**, **W4_us**, **W4Min_us**, **W4Max_us**: Timing parameters in milliseconds used for the initialization pattern. A detailed description of the parameters is available on the Vector **K-Line Protocol Reference Chart** e.g. available at vector.com.
- **addressNot**: The inverted address to be sent by the ECU simulation. A value of 0 will use the default, i.e. the inverted 5 baud address.

## Return Values

On success 0, otherwise a value less than 0.

## Example

```plaintext
on preStart
{
  long klineHandle;
  long channelNo;
  long value;

  channelNo = DiagGetCommParameter("CANoe.ChannelNumber");
  klineHandle = KLine_CreateECURepresentation(channelNo);
  write("KLine_CreateECURepresentation at K-Line%d returns %d", channelNo, klineHandle);

  value = DiagGetCommParameter("KLine.InitType");
  if (value == 1 /*FIVE_BAUD*/)
  {
    // For a 5 Baud ECU the initialization of the parameters must be done in prestart!
    value = diagGetCommParameter("KLine.5BaudAddress");
    // The timing parameters from the configuration are for the tester side, so use hard-coded ones here
    status = KLine_Init5BaudEcuParams(value, 50 /* 5Bd */, 100, 10, 1, 35, 0, 650, 0 /*default*/);
    write("Init 5Bd pattern for address 0x%02x returns %d", value, status);
  }
}
```
