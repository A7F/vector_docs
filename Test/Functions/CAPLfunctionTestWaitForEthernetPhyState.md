# TestWaitForEthernetPhyState

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long TestWaitForEthernetPhyState(ethernetport hwport, long state, dword aTimeout);
```

## Description

Waits for the occurrence of the specified Ethernet PHY state. Should the Ethernet PHY state not occur before the expiration of the time **aTimeout**, the wait condition is resolved nevertheless. If the Ethernet PHY has already the expected state, the function returns immediately with return value 1.

## Parameters

- **hwPort**: Hardware port qualifier.
- **state**:
  - 1: normal state
  - 2: sleep state
  - 3: power off state
  - 4: sleep request
  - 5: sleep local state
  - 6: sleep local request
- **aTimeout**: Maximum time that should be waited [ms] (Transmission of 0: no timeout controlling).

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, for example, functionality is not available
- **0**: Resume due to timeout
- **1**: Resume due to event occurred

## Example

—

[TestJoinEthernetPhyState](CAPLfunctionTestJoinEthernetPhyState.md) • [ethGetPhyState](../../IP/Functions/CAPLfunctionEthGetPhyState.md) • [ethSetPhyState](../../IP/Functions/CAPLfunctionEthSetPhyState.md) • [on ethernetPhyState](../../IP/EventProcedures/CAPLfunctionOnEthernetPhyState.md)
