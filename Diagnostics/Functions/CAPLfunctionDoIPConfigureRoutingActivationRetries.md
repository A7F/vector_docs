# DoIP_ConfigureRoutingActivationRetries

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
void DoIP_ConfigureRoutingActivationRetries(dword numberOfRetries,
dword retryPeriod_ms, byte nackCodes[], dword nackCodesCount);
```

## Description

Allows to activate or deactivate DoIP routing activation retries. Retries are only attempted for specific negative ACK codes that can be given in a list of codes. There is a default list that is used when **nackCodesCount** is **0**.

## Parameters

- **numberOfRetries**: Routing activation will be retried this many times. The feature can be deactivated with a value of **0** (default).
- **retryPeriod_ms**: Time to wait between the failure of the routing activation and the next try. Must be **> 0** if numberOfRetries is **> 0**.
- **nackCodes**: Array of negative ACK codes that will lead to a retry.
- **nackCodesCount**: Number of negative ACK codes in the array. If this value is **0**, a default will be activated that consists of the values **0x04** and **0x11**.

## Return Values

—

## Example

```plaintext
ActivateRetries()
{
  byte nackCodes[1];
  // Perform up to 3 retries when the default codes 0x04 or 0x11 are returned
  DoIP_ConfigureRoutingActivationRetries(3, 100, nackCodes, 0);
}

DeactivateRetries()
{
  byte nackCodes[1];
  // Turn off retries
  DoIP_ConfigureRoutingActivationRetries(0, 0, nackCodes, 0);
}
```

[DoIP_ConfigureRoutingActivationRequest](CAPLfunctionDoIPConfigureRoutingActivationRequest.md) • [DoIP_ConfigureRoutingActivationResponse](CAPLfunctionDoIPConfigureRoutingActivationResponse.md) • [_DoIP_RoutingActivationRequest](CAPLfunctionDoIPRoutingActivationRequest.md)
