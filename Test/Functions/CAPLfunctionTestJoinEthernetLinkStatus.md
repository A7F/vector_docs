# TestJoinEthernetLinkStatus

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestJoinEthernetLinkStatus(long channel, long status); // form 1`
- `long TestJoinEthernetLinkStatus(long channel, Int64 hwChannel, long status); // form 2`
- `long TestJoinEthernetLinkStatus(ethernetport hwport, long status); // form 3`

## Description

Completes the current set of **joined events** with the transmitted event. This function does not wait.

**Note:** Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **channel**: Ethernet channel number.  
  Value range: 1..32

- **hwChannel**: Ethernet hardware channel number.  
  Value range: 1..64

- **hwPort**: Hardware port qualifier.

- **Status**: Wait for this status:
  - 0 = link down
  - 1 = link up

- **aTimeout**: Maximum time that should be waited [ms] (Transmission of 0: no timeout controlling).

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, for example, functionality is not available
- **> 0**: Resume due to timeout

## Example

—

[TestWaitForEthernetLinkStatus](CAPLfunctionTestWaitForEthernetLinkStatus.md) • [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md) • [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md) • [ethGetLinkStatus](../../IP/Functions/CAPLfunctionEthGetLinkStatus.md) • [ethSetLinkStatus](../../IP/Functions/CAPLfunctionEthSetLinkStatus.md)
