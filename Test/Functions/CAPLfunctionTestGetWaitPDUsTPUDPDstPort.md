# TestGetWaitPDUsTPUDPDstPort

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestGetWaitPDUsTPUDPDstPort(dword &udpDestinationPort); //form 1`
- `long TestGetWaitPDUsTPUDPDstPort(dword explicitJoinIndex, dword &udpDestinationPort); //form 2`

## Description

If a PDU was received via UDP that triggered the last wait function, with form 1 the UDP destination port can be requested.

Form 2 can only be used for joined events. The number of the joined event (return value of **TestJoin...**) is here being used as an index.

## Parameters

- **udpDestinationPort**: UDP destination port.
- **explicitJoinIndex**: Number of the joined event corresponds with the return value of **TestJoin...**.

## Return Values

- **0**: Data access successful.
- **-1**: Data access could not be executed, the last event was not a PDU event.
- **-2**: Data access could not be executed; the **explicitJoinIndex** is out-of-range.

## Example

```c
testcase TC_CheckPDUTPProperties()
{
  dword srcAddr, dstAddr, srcPort, dstPort;
  if (TestWaitForPDU(engineDataPDU, 0, 200)!=1)
  {
    TestStepFail("PDU not received");
  }
  else
  {
    if (TestGetWaitPDUsTPIPv4SrcAddr(srcAddr)==0
        && TestGetWaitPDUsTPIPv4DstAddr(dstAddr)==0
        && TestGetWaitPDUsTPUDPSrcPort(srcPort)==0
        && TestGetWaitPDUsTPUDPDstPort(dstPort)==0)
    {
      if (srcAddr != IpGetAddressAsNumber("192.168.0.1"))
        TestStepFail("source address not matching");
      else if (dstAddr != IpGetAddressAsNumber("192.168.0.2"))
        TestStepFail("destination address not matching");
      else if (srcPort != 1234)
        TestStepFail("source port not matching");
      else if (dstPort != 4321)
        TestStepFail("destination port not matching");
    }
    else
      TestStepFail("could not retrieve expected PDU TP properties");
  }
}
```

**Related Links**

- [TestWaitForPDU](CAPLfunctionTestWaitForPDU.md) • [TestGetWaitPDUData](CAPLfunctionTestGetWaitPDUData.md) • [TestGetWaitPDUsTPIPv4DstAddr](CAPLfunctionTestGetWaitPDUsTPIPv4DstAddr.md) • [TestGetWaitPDUsTPIPv4SrcAddr](CAPLfunctionTestGetWaitPDUsTPIPv4SrcAddr.md) • [TestGetWaitPDUsTPIPv6DstAddr](CAPLfunctionTestGetWaitPDUsTPIPv6DstAddr.md) • [TestGetWaitPDUsTPIPv6SrcAddr](CAPLfunctionTestGetWaitPDUsTPIPv6SrcAddr.md) • [TestGetWaitPDUsTPTCPDstPort](CAPLfunctionTestGetWaitPDUsTPTCPDstPort.md) • [TestGetWaitPDUsTPTCPSrcPort](CAPLfunctionTestGetWaitPDUsTPTCPSrcPort.md) • [TestGetWaitPDUsTPUDPSrcPort](CAPLfunctionTestGetWaitPDUsTPUDPSrcPort.md)
