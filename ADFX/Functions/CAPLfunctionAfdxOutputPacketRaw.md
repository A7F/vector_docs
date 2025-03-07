[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADFX/Functions/CAPLfunctionAfdxOutputPacketRaw.md)

**CAPL Functions** » **AFDX** » **AfdxOutputPacketRaw**

# AfdxOutputPacketRaw

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**  
This function was renamed from **AfdxOutputRawPacket** in your CANoe DE product version 8.1.

## Function Syntax

```plaintext
long AfdxOutputPacketRaw(long packet);
```

## Description

The specified AFDX message is transmitted without considering the internal AFDX software stack.  
This call is equivalent to `AfdxOutputPacket( packet, SingleShot, NoIPFragmentation, NoAFDXVLScheduling, NoAFDXSeqNoManagement, MACIFRelated )`.

## Parameters

- **packet**: handle of the message to send that has been created with [AfdxInitPacket](CAPLfunctionAfdxInitPacket.md).

## Return Values

- **0**
- **other value**: [error code](../CAPLfunctionsAFDXErrorCodes.md)

## Example

```plaintext
includes
{
  #include "AFDX/Utils.cin"
}

Node System - preStart in CAPL Browser

on preStart
{
  long result;
  result = AfdxRegisterReceiveCallback("OnAfdxRawPacket", BothDirections, NotDropped, EveryFrameAndPacket);
}

Node Callback Function in CAPL Browser

void OnAfdxRawPacket(long dir, long line, int64 timestamp, long bag, long afdxFlags, long packet)
{
  long packetHandle;

  if (afdxFlags & packetIsReassembled)
  {
    write("<%NODE_NAME%> OnAfdxRawPacket  packet is JumboPacket --> skip");
    return; // don't transfer Jumbo-frames
  }

  if (getBusContext() == gContextAfdx1)
  {
    setBusContext(gContextAfdx2);
  }
  else
  {
    setBusContext(gContextAfdx1);
  }

  packetHandle = AfdxInitPacket(packet);
  if (packetHandle == 0) {
    write("<%NODE_NAME%> AfdxInitPacket failed");
    return;
  }

  // modify signals only if not a fragment
  if (!(packetIsFragmented & afdxFlags))
  {
    // TBD
  }
  else
  {
    // must use direct byte access to manipulate
  }

  AfdxOutputPacketRaw(packetHandle);
  AfdxReleasePacket(packetHandle);
}
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)