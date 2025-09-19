[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/FlexRay/Functions/CAPLfunctionFRGwBypassDynamic.md)

**CAPL Functions** » [FlexRay](../CAPLfunctionsFlexrayOverview.md) » frGwBypassDynamic

# frGwBypassDynamic

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long frGwBypassDynamic(long bypass, long channel);
```

## Description

Activates/deactivates the automatic routing for the dynamic part. The function cannot be used during a measurement.

Settings from the **Network Hardware Configuration** dialog are overwritten with this function.

## Parameters

- **bypass**:
  - 0 = Routing deactivated
  - 1 = Routing activated

- **channel**: Output channel of the gateway.

## Return Values

- **0**: Error
- **1**: OK

## Example

```plaintext
...
frGwBypassDynamic(0,1)
// The gateway routing for the dynamic part will be deactivated 
// for the gateway that uses channel 1.
...
```

[FlexRay Gateway Mode](../../../CANoeCANalyzer/FlexRay/FlexRayGatewayMode.md)

---

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
