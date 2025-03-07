[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/EventProcedures/CAPLfunctionOnPDU.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Event Procedures](../CAPLfunctionsEventProceduresOverview.md) » on PDU

# on PDU

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `on PDU <PDU name>;`
- `on PDU short <short header ID>;`
- `on PDU long <long header ID>;`
- `on PDU <header ID>;`
- `on PDU *;`
- `on PDU [*];`

## Description

This event procedure is called if the corresponding PDU is received of which the updated bit is set or undefined.

For the event procedure of type `*` and `[*]`, keyword [this](CAPLfunctionKeywordThis.md) is an untyped [PDU object](../Objects/CAPLfunctionPDU.md). For all other event procedures, keyword **this** is a typed **PDU object**.

**Note:** The form **on pdu \*** is also called for SOME/IP PDUs. Keyword **this** is an untyped [PDU object](../Objects/CAPLfunctionPDU.md). The data contains the SOME/IP header and payload. Security selectors are not available.

## Parameters

—

## Selectors

—

## Example

**Example 1**

```plaintext
on PDU short 5
{
  write("on pdu: %s", this.name);
}
```

**Example 2**

```plaintext
on PDU EngineData
{
  write("EngineData received at: %d s", this.time);
}
```

**Example 3**

```plaintext
on PDU *
{
  write("on pdu: LongHeaderID %X length %d", this.LongHeaderID, this.PduLength);
}
```

[Resolution of Ambiguities](../../../Shared/CAPL/General/ResolveAmbiguities.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)