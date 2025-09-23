[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/KLine/Functions/CAPLfunctionKLineCreateECURepresentation.md)

**CAPL Functions** » **K-Line** » **KLine_CreateECURepresentation**

# KLine_CreateECURepresentation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long KLine_CreateECURepresentation(dword channel)
```

## Description

Initialize K-Line ECU communication on given channel.

**Note**: Must be called in **on preStart** handler.

## Parameters

- **channel**: Number of the hardware channel.

## Return Values

On success 0, otherwise a value less than 0.

## Example

```plaintext
on preStart
{
   long klineHandle;
   long channelNo;

   channelNo = DiagGetCommParameter("CANoe.ChannelNumber");
   klineHandle = KLine_CreateECURepresentation(channelNo);
   write("KLine_CreateECURepresentation at K-Line%d returns %d", channelNo, klineHandle);
}
```
