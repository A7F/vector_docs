[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/KLine/Functions/CAPLfunctionKLineGetMeasuredInitParameter.md)

**CAPL Functions** » **K-Line** » **KLine_GetMeasuredInitParameter**

# KLine_GetMeasuredInitParameter

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long KLine_GetMeasuredValue(dword parameterID)
```

## Description

Retrieves the different parameters of the init patterns.

## Parameters

- **parameterID**  
  Value range: 0-10  
  0: KeyByte1  
  1: Keybyte2  
  2: TiniL  
  3: Twup  
  4: W4 between key byte 2 and inverted key byte 2  
  5: W1  
  6: W2  
  7: W3  
  8: W4  
  9: W4 between inverted keybyte 2 and inverted address byte  
  10: BaudRate from sync pattern

## Return Values

Parameter value or [error code](../../Diagnostics/CAPLfunctionsDiagnosticsErrorCode.md).

## Example

```c
DiagRequest StartDiagnosticSession req;
enum eMeasuredValues
{
   KeyByte1            = 0,
   KeyByte2            = 1,
   TiniL               = 2,
   Twup                = 3,
   W4Time1             = 4,
   InvertedAddressByte = 5,
   W1Time              = 6,
   W2Time              = 7,
   W3Time              = 8,
   W4Time2             = 9,
   BaudRateSyncByte    = 10
};

long pKeyByte1;
long pKeyByte2;
long pW4Time1;
long pInvertedAddressByte;
long pW1Time;
long pW2Time;
long pW3Time;
long pW4Time2;
long pBaudRateSyncByte;

DiagSetTarget("DUT");
DiagConnectChannel();
   if (1 == TestWaitForDiagChannelConnected(3000))
   {
      TestStepPass("Channel connected successfully");
   }
   else
   {
      TestStepFail("Could not connect channel");
   }

req.SendRequest();
   if (1 == testWaitForDiagKLineFrameTransmitted(1000))
   {
      TestStepPass("Request transmitted successfully.");
   }
   else
   {
      TestStepFail("No request transmitted.");
   }

pKeyByte1 = KLine_GetMeasuredInitParameter(KeyByte1);
pKeyByte2 = KLine_GetMeasuredInitParameter(KeyByte2);
pW4Time1 = KLine_GetMeasuredInitParameter(W4Time1);
pInvertedAddressByte = KLine_GetMeasuredInitParameter(InvertedAddressByte);
pW1Time = KLine_GetMeasuredInitParameter(W1Time);
pW2Time = KLine_GetMeasuredInitParameter(W2Time);
pW3Time = KLine_GetMeasuredInitParameter(W3Time);
pW4Time2 = KLine_GetMeasuredInitParameter(W4Time2);
pBaudRateSyncByte = KLine_GetMeasuredInitParameter(BaudRateSyncByte);

write("KeyByte1: 0x%x", pKeyByte1);
write("KeyByte2: 0x%x", pKeyByte2);
write("W4Time 1: %.2f", pW4Time1/toMs);
write("InvertedAddressByte: 0x%x", pInvertedAddressByte);
write("W1Time: %.2f", pW1Time/toMs);
write("W2Time: %.2f", pW2Time/toMs);
write("W3Time: %.2f", pW3Time/toMs);
write("W4Time 2: %.2f", pW4Time2/toMs);
write("BaudRateSyncByte: %d", pBaudRateSyncByte);

DiagCloseChannel();
   if (1 == testWaitforDiagChannelClosed(1000))
   {
      TestStepPass("Diag channel closed successfully");
   }
   else
   {
      TestStepFail("Diag channel could not be closed.");
   }
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
