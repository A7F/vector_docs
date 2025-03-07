[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xGetTokenOidElement.md)

**CAPL Functions** » **Car2x** » **C2xGetTokenOidElement**

# C2xGetTokenOidElement

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long C2xGetTokenOidElement(long packet, char protocolDesignator[], char tokenDesignator[], long index);
```

## Description

This function gets an element of the [ASN.1](../../../CANoeCANalyzer/Car2x/protocols/ASN1.md) datatype OID (Object Identifier or Relative OID) that is specified by its index to a new value.

## Parameters

- **packet**: Handle of a packet.
- **protocolDesignator**: Name of the protocol.
- **tokenDesignator**: Name of the token.
- **index**: Zero based index of the element.

## Return Values

Value of the element. With [C2xGetLastError](CAPLfunctionC2xGetLastError.md) you can check if the function has been processed successfully.

## Example

```c
// Callback function on receiving IVIM messages
void OnRxIVIM(long channel, long dir, long radioChannel, long signalStrength, long signalQuality, long packet)
{
  // Gets the second value of the OID
  long elementValue = C2xGetTokenOidElement(packet, "IVIM", "ivi.optional[0].isc[0].infrastructureSupport.baseOid", 1);
}
```

[See Also](javascript:void(0);)