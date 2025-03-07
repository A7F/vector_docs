[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForLinSpike.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestWaitForLinSpike

# TestWaitForLinSpike

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long TestWaitForLinSpike (dword aTimeout);
```

## Description

Waits for the occurrence of a LIN Spike event. Should the event not occur before the expiration of the time **aTimeout**, the wait condition is resolved nevertheless.

**Note**: Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aTimeout**: Maximum time that should be waited [ms]. (Transmission of 0: no timeout controlling)

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, for example, functionality is not available
- **0**: Resume due to timeout
- **1**: Resume due to event occurred

## Example

```c
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

[TestGetWaitLinSpikeData](CAPLfunctionTestGetWaitLinSpikeData.md) • [TestJoinLinSpike](CAPLfunctionTestJoinLinSpike.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)