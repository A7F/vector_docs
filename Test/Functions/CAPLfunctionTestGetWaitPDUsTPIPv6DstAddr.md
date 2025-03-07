[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestGetWaitPDUsTPIPv6DstAddr.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestGetWaitPDUsTPIPv6DstAddr

# TestGetWaitPDUsTPIPv6DstAddr

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestGetWaitPDUsTPIPv6DstAddr(byte IPv6DestinationAddress[]); //form 1`
- `long TestGetWaitPDUsTPIPv6DstAddr(dword explicitJoinIndex, byte IPv6DestinationAddress[]); //form 2`

## Description

If a PDU was received via IPv6 that triggered the last wait function, with form 1 the IPv6 destination address can be requested.

Form 2 can only be used for joined events. The number of the joined event (return value of **TestJoin...**) is here being used as an index.

## Parameters

- **IPv6DestinationAddress**: IPv6 destination address as 16 byte array.
- **explicitJoinIndex**: Number of the joined event corresponds with the return value of **TestJoin...**.

## Return Values

- **0**: Data access successful.
- **-1**: Data access could not be executed, the last event was not a PDU event.
- **-2**: Data access could not be executed; the **explicitJoinIndex** is out-of-range.

## Example

```c
long IPv6AddressEquals(byte addr1[], byte addr2[])
{
  int i;
  if (elcount(addr1)<16 || elcount(addr2)<16)
    return 0;

  for (i=0; i< 16; ++i)
    if (addr1[i]!=addr2[i])
      return 0;

  return 1;
}

testcase TC_CheckPDUTPProperties()
{
  dword srcPort, dstPort;
  byte  srcAddr[16], dstAddr[16], expectedSrcAddr[16], expectedDstAddr[16];
  if (TestWaitForPDU(engineDataPDU, 0, 200)!=1)
  {
    TestStepFail("PDU not received");
  }
  else
  {
    if (TestGetWaitPDUsTPIPv6SrcAddr(srcAddr)==0
        && TestGetWaitPDUsTPIPv6DstAddr(dstAddr)==0
        && TestGetWaitPDUsTPUDPSrcPort(srcPort)==0
        && TestGetWaitPDUsTPUDPDstPort(dstPort)==0)
    {
      IpGetAddressAsArray("2001::1", expectedSrcAddr);
      IpGetAddressAsArray("2001::2", expectedDstAddr);

      if (IPv6AddressEquals(srcAddr, expectedSrcAddr)!=1)
        TestStepFail("source address not matching");
      else if (IPv6AddressEquals(dstAddr, expectedDstAddr)!=1)
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

[TestWaitForPDU](CAPLfunctionTestWaitForPDU.md) • [TestGetWaitPDUData](CAPLfunctionTestGetWaitPDUData.md) • [TestGetWaitPDUsTPIPv4DstAddr](CAPLfunctionTestGetWaitPDUsTPIPv4DstAddr.md) • [TestGetWaitPDUsTPIPv4SrcAddr](CAPLfunctionTestGetWaitPDUsTPIPv4SrcAddr.md) • [TestGetWaitPDUsTPIPv6SrcAddr](CAPLfunctionTestGetWaitPDUsTPIPv6SrcAddr.md) • [TestGetWaitPDUsTPTCPDstPort](CAPLfunctionTestGetWaitPDUsTPTCPDstPort.md) • [TestGetWaitPDUsTPTCPSrcPort](CAPLfunctionTestGetWaitPDUsTPTCPSrcPort.md) • [TestGetWaitPDUsTPUDPDstPort](CAPLfunctionTestGetWaitPDUsTPUDPDstPort.md) • [TestGetWaitPDUsTPUDPSrcPort](CAPLfunctionTestGetWaitPDUsTPUDPSrcPort.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)