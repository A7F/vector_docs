# C2xGetTokenPhys

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
double C2xGetTokenPhys(long packet, char[] protocolDesignator, char[] tokenDesignator)
```

## Description

This function returns the physical value of the existing ASN.1 token in the packet. This function succeeds only if following requirements apply:

- The token path specified by the tokenDesignator parameter exists and belongs to ASN.1 part of the message, setting the physical value for lower protocols like GeoNet or WSMP is not supported.
- The ASN.1 token specified by the tokenDesignator parameter has a raw/physical value conversion factor defined in the database (column **Format** in the Car2x Network Explorer must not be empty for this ASN.1 token).

## Parameters

- **packet**: Handle of a packet that has been created with C2xInitPacket or was provided as callback function parameter.
- **protocolDesignator**: Name of the protocol, e.g. CAM.
- **tokenDesignator**: Name of the ASN.1 token, e.g. cam.camParameters.basicContainer.referencePosition.latitude.

## Return Values

With `C2xGetLastError` you can check if the function has been processed successfully.

- **0**: —
- **≠0**: Physical value of the token

## Example

```plaintext
void OnPreTxDENM(LONG packet)
{
  write("DENM event positition latitude %f°", C2xGetTokenPhys(packet, "DENM" "denm.management.eventPosition.latitude"));
}
```
