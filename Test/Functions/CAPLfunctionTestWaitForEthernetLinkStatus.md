[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForEthernetLinkStatus.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestWaitForEthernetLinkStatus

# TestWaitForEthernetLinkStatus

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestWaitForEthernetLinkStatus(long channel, long status, dword aTimeout); // form 1`
- `long TestWaitForEthernetLinkStatus(long channel, Int64 hwChannel, long status, dword aTimeout); // form 2`
- `long TestWaitForEthernetLinkStatus(ethernetport hwport, long status, dword aTimeout); // form 3`

## Description

Waits for the occurrence of the specified Ethernet link status. Should the Ethernet link status not occur before the expiration of the time **aTimeout**, the wait condition is resolved nevertheless. If the Ethernet link has already the expected state, the function returns immediately with return value 1.

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
- **0**: Resume due to timeout
- **1**: Resume due to event occurred

## Example

```c
void MainTest ()
{
  long result;
  dword timeout;
  ethernetport myEthernetPort;

  // form 1 - waits for link status up to occur on channel 1
  result = TestWaitForEthernetLinkStatus(1, 1, timeout);

  // form 2 - waits for link status up to occur on hardware channel 3 of channel 1
  result = TestWaitForEthernetLinkStatus(1, 3, 1, timeout);

  // form 3 - waits for link status down to occur on myEthernetPort;
  result = TestWaitForEthernetLinkStatus(myEthernetPort, 0, timeout);
}
```

[TestJoinEthernetLinkStatus](CAPLfunctionTestJoinEthernetLinkStatus.md) • [ethGetLinkStatus](../../IP/Functions/CAPLfunctionEthGetLinkStatus.md) • [ethSetLinkStatus](../../IP/Functions/CAPLfunctionEthSetLinkStatus.md) • [on ethernetStatus](../../IP/EventProcedures/CAPLfunctionOnEthernetStatus.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)