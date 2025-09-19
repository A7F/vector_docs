# C2xSetTokenOidElement

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long C2xSetTokenOidElement(long packet, char protocolDesignator[], char tokenDesignator[], long index, long value);
```

## Description

This function sets an element of the [ASN.1](../../../CANoeCANalyzer/Car2x/protocols/ASN1.md) datatype OID (Object Identifier or Relative OID) that is specified by its index to a new value.

## Parameters

- **packet**: Handle of a packet.
- **protocolDesignator**: Name of the protocol.
- **tokenDesignator**: Name of the token.
- **index**: Zero based index of the element.
- **value**: New value of the element.

## Return Values

- **0**: No error, OK
- **≠0**: [Error code](../CAPLfunctionsCar2xErrorCodes.md)

## Example

```plaintext
// Callback function before sending IVIM messages from IL
void OnPreTxIVIM(long packet)
{
  // Set the first element of the Oid to 42
  C2xSetTokenOidElement(packet, "IVIM", "ivi.optional[0].isc[0].infrastructureSupport.baseOid", 0, 42);
}
```
