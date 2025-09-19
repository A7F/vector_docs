[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestGetWaitLinSpikeData.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestGetWaitLinSpikeData

# TestGetWaitLinSpikeData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long TestGetWaitLinSpikeData (linSpikeEvent apEvent);
long TestGetWaitLinSpikeData (dword index, linSpikeEvent apEvent);
```

## Description

If LIN Spike is the last event that triggers a wait instruction, the frame content can be called up with the first function.

The second function can only be used for **joined events**. The number of the **joined event** (return value of `testJoin...`) is here being used as an index.

## Parameters

- **apEvent**: Event variable that should be filled in with this function.
- **index**: Number of the **joined event** corresponds with the return value of `testJoin...`.

## Return Values

- **0**: Data access successful
- **-1**: Data access could not be executed, the last event was not an awaited event.

## Example

```plaintext
testcase tcTFS_linSpikeEvent ()
{
   linSpikeEvent linSpikeEventData;
   if (testWaitForLinSpike (5000) == 1)
   {
      if (testGetWaitLinSpikeData(linSpikeEventData) == 0)
      {
         testStep("Evaluation", "LIN Spike event occurred. Signal length is %d ns", linSpikeEventData.length_ns);
      }
   }
}
```

[TestWaitForLinSpike](CAPLfunctionTestWaitForLinSpike.md) • [TestJoinLinSpike](CAPLfunctionTestJoinLinSpike.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
