[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/AUTOSARpduIL/Functions/CAPLfunctionApplPDUilTxPending.md)

**CAPL Functions** » **AUTOSAR PDU IL** » **applPDUILTxPending**

# applPDUILTxPending

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
The CAPL program may define these optional functions (all marked with the prefix **appl**) to receive indications about events from the IL.  
**Caution**: Within this callback the **setSignal** functionality must not be used, since it might trigger further unwanted transmissions.

## Function Syntax

```plaintext
dword applPDUILTxPending (dword busContext, dword shortID, dword longID, char name[], dword & aPDULength, byte data[]);
```

## Description

This callback is optionally being called before the IL sends a PDU to the bus. In this callback it is possible to prevent the sending of the PDU or to change the data of the PDU.

## Parameters

- **busContext**: The context of the simulation bus this PDU will be sent.
- **shortID**: With the ID you can identify the PDU.
- **longID**: With the ID you can identify the PDU.
- **name**: With the name you can identify the PDU.
- **aPDULength**: The payload length of the PDU to be sent and the length of the data bytes array.
- **data**: Data bytes array with the bytes to be sent. The bytes can optionally be changed.

## Return Values

- **0**: sending of the PDU with the supplied info is prevented. Alternatively use the [fault injection interface](../CAPLfunctionsAUTOSARpduILOverview.md#FaultInjectionAndDisturbance) to prevent the sending of a PDU.
- **1**: sending of the PDU with the supplied info is done.

## Example

**Individual calculation of a message counter:**

```plaintext
variables
{
  dword counterValue;
}

on PDU PDU_001
{
  counterValue = this.MessageCounter; // store current message counter value in global variable
}

dword applPDUILTxPending (dword busContext, dword shortID, dword longID, char name[], dword & aPDULength, byte data[])
{
  dword i;

  // PDU "PDU_001" contains a 8-Bit message counter in Byte 0.
  if(strncmp(name, "PDU_001", elcount(name)) == 0)
  {
    data[0] = (counterValue + 1) % 256;
  }
  return 1; // don't prevent sending of the PDU
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)