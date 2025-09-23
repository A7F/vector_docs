[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINtpFirstFrameIndication.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » LINtp_FirstFrameIndication

# LINtp_FirstFrameIndication

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void LINtp_FirstFrameIndication(long sender, long receiver, long announcedLen);
```

## Description

Indicates the start of a segmented reception.

## Parameters

- **sender**: Address of sender node, or 0 for master.
- **receiver**: Address of receiver node, or 0 for master.
- **announcedLen**: Number of bytes to be expected.

## Return Values

—

## Example

```plaintext
LINtp_FirstFrameIndication(long sender, long receiver, long announcedLen)
{
  write("Start reception of %d bytes", announcedLen);
}
```

•  Technical References are only available in English
