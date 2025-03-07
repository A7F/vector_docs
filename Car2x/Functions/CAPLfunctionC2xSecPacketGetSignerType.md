[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xSecPacketGetSignerType.md)

**CAPL Functions** » **Car2x** » C2xSecPacketGetSignerType

# C2xSecPacketGetSignerType

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Function Syntax

```plaintext
long C2xSecPacketGetSignerType(long packetHandle);
```

## Description

Retrieves how the message signer information is included in the message. The information can be transmitted as digest (HashedId8), certificate or certificate chain.

## Parameters

- **packetHandle**: Handle of the signed packet.

## Return Values

- **0**: unsecured
- **1**: digest
- **2**: certificate
- **3**: certificate chain

## Example

```plaintext
switch (C2xSecPacketGetSignerType(packetHandle))
{
    case 0: // unsecured
        // ...
        break;
    case 1: // digest
        // ...
        break;
    case 2: // certificate
        // ...
        break;
    case 3: // certificate chain
        // ...
        break;
    default: // error
        // ...
        break;
}
```

[See Also](javascript:void(0);)