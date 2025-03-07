[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestGetWaitEventMostPkt.md)

**CAPL Functions** » **Test Feature Set** » **TestGetWaitEventMostPkt**

# TestGetWaitEventMostPkt

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long TestGetWaitEventMostPkt();`
- `long TestGetWaitEventMostPkt(dword aIndex);`

## Description

If the last (single) wait condition was resolved by a MOST packet event, the first function makes the packet data accessible by the packet API functions normally used within the [onMostPkt()](../../MOST/EventProcedures/CAPLfunctionOnMOSTPkt.md) event handler, such as mostPktSrcAdr(), mostPktDestAdr(), mostPktGetData() etc.

The second function can only be used for "joined events". The number of the "joined event" (return value of "testJoin...") is here being used as an index.

Once another wait condition is set up in the current test sequence, access to the packet data will be no longer available.

## Parameters

- **aIndex**: Number of the "joined event" that was resumed by a MOST packet event. The number corresponds to return value of the "testJoin..." function call, by which the event was added to a joined condition.

## Return Values

- **0**: Successful data access
- **-1**: Data access can’t be executed, since the last wait condition was not resolved by a MOST packet event.

## Example

```plaintext
// Access to packet data:
  if(testWaitForMostPkt("AudioDiskPlayer.MediaInfo.Status", 1, 500) == 1)
  {
    byte data[1524];
    long pktSize;
    testGetWaitEventMostPkt();
    pktSize = mostPktGetData(data, elCount(data));
    if(pktSize > 5)
    {
      testStepPass("Packet test", "%d bytes received", pktSize);
    }
    else
    {
      testStepFail("Packet test");
    }
  }
```

[TestWaitForMostPkt](CAPLfunctionTestWaitForMostPkt.md) • [TestWaitForMostSpyPkt](CAPLfunctionTestWaitForMostSpyPkt.md) • [TestJoinMostPktEvent](CAPLfunctionTestJoinMostPktEvent.md) • [TestJoinMostSpyPktEvent](CAPLfunctionTestJoinMostSpyPktEvent.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)