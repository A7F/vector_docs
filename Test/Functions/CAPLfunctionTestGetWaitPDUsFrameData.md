[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestGetWaitPDUsFrameData.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestGetWaitPDUsFrameData

# TestGetWaitPDUsFrameData

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestGetWaitPDUsFrameData (message * msg); // form 1`
- `long TestGetWaitPDUsFrameData (ethernetPacket * packet); // form 2`
- `long TestGetWaitPDUsFrameData (FrFrame * frame); // form 3`
- `long TestGetWaitPDUsFrameData (dword explicitJoinIndex, message * msg); // form 4`
- `long TestGetWaitPDUsFrameData (dword explicitJoinIndex, ethernetPacket * packet); // form 5`
- `long TestGetWaitPDUsFrameData (dword explicitJoinIndex, FrFrame * frame); // form 6`

## Description

If a valid PDU is the last event that triggers a wait instruction, the message’s, packet’s or frame’s content that contained the PDU can be called up with form 1-3.

Form 4-6 can only be used for joined events. The number of the joined event (return value of TestJoin...) is here being used as an index.

## Parameters

- **frame**: Message variable of type CAN message, Ethernet Packet or FlexRay frame that should be filled in with this function. It has to be either a type free message variable, or a message variable that was created for the PDU type that triggered the wait instruction.
- **explicitJoinIndex**: Number of the **joined event** corresponds with the return value of `TestJoin...`.

## Return Values

- **0**: Data access successful.
- **-1**: Data access could not be executed, the last event was not a PDU event or the **explicitJoinIndex** is out-of-range.
- **-2**: Data access could not be executed; Wrong bus system; Ethernet packet/CAN message/FlexRay frame is not available.

## Example

```plaintext
testcase Test_01()
{
  long ret;
  PDU PDU_A aPDU_01;
  message * aMsg_01;

  ret = TestWaitForPDU(dbPDU::PDU_A, 0, 250);

  if(ret != 1)
  {
    TestStepFail("Error: PDU not received");
  }
  else
  {
    ret = TestGetWaitPDUsFrameData(aMsg_01); // PDU is assumed to be sent on CAN
    if(ret != 0)
    {
      TestStepFail("Error: Can not access PDU");
    }
    else
    {
      TestStepPass("OK", "Received PDU in message with CAN ID %lu", aMsg_01.ID);
    }
  }
}
```

## Related Links

- [TestWaitForPDU](CAPLfunctionTestWaitForPDU.md)
- [TestGetWaitPDUData](CAPLfunctionTestGetWaitPDUData.md)
- [TestGetWaitPDUsTPIPv6SrcAddr](CAPLfunctionTestGetWaitPDUsTPIPv6SrcAddr.md)
- [TestGetWaitPDUsTPIPv6DstAddr](CAPLfunctionTestGetWaitPDUsTPIPv6DstAddr.md)
- [TestGetWaitPDUsTPIPv4SrcAddr](CAPLfunctionTestGetWaitPDUsTPIPv4SrcAddr.md)
- [TestGetWaitPDUsTPIPv4DstAddr](CAPLfunctionTestGetWaitPDUsTPIPv4DstAddr.md)
- [TestGetWaitPDUsTPUDPSrcPort](CAPLfunctionTestGetWaitPDUsTPUDPSrcPort.md)
- [TestGetWaitPDUsTPUDPDstPort](CAPLfunctionTestGetWaitPDUsTPUDPDstPort.md)
- [TestGetWaitPDUsTPTCPSrcPort](CAPLfunctionTestGetWaitPDUsTPTCPSrcPort.md)
- [TestGetWaitPDUsTPTCPDstPort](CAPLfunctionTestGetWaitPDUsTPTCPDstPort.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
