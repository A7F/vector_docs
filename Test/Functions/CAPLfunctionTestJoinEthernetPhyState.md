# TestJoinEthernetPhyState

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long TestJoinEthernetPhyState(ethernetport hwport, long state);
```

## Description

Completes the current set of joined events with the transmitted event. This function does not wait.

**Note**  
Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **hwPort**: Hardware port qualifier.
- **state**: Wait for this state:
  - 1: normal state
  - 2: sleep state
  - 3: power off state
  - 4: sleep request
  - 5: sleep local state
  - 6: sleep local request

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, for example, functionality is not available
- **>0**: Number of the joined event

## Example

```c
void MainTest ()
{
  long result;
  ethernetport myEthernetPort = ethernetport::Ethernet1::myPort;

  // form 1 - waits for PHY state "normal" to occur on myEthernetPort;
  result = TestWaitForEthernetPhyState(myEthernetPort, 0, timeout);
}
```

[TestWaitForEthernetPhyState](CAPLfunctionTestWaitForEthernetPhyState.md) • [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md) • [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md) • [ethGetPhyState](../../IP/Functions/CAPLfunctionEthGetPhyState.md) • [ethSetPhyState](../../IP/Functions/CAPLfunctionEthSetPhyState.md)
