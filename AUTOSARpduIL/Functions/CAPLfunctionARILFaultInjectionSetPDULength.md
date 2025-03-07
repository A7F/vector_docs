[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/AUTOSARpduIL/Functions/CAPLfunctionARILFaultInjectionSetPDULength.md)

**CAPL Functions » AUTOSAR PDU IL » ARILFaultInjectionSetPDULength**

# ARILFaultInjectionSetPDULength

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**

Your CANoe DE product uses internally for each PDU a buffer, which has a size of 32 bytes or, if the PDU is larger, corresponds exactly to the size of the PDU. With fault injection, it is only possible to set values for the PDU payload length between 0 and the available buffer size. This results in the following:

- Fault injection value for PDU length ≤ PDU length in database:
  - The payload length of the PDU will be set to the provided fault injection value.
- Fault injection value for PDU length > PDU length in database:
  - Provided fault injection value ≤ 32:
    - The payload length of the PDU will be set to the provided fault injection value.
  - Provided fault injection value > 32:
    - The larger of the two values 32 and PDU length in the database will be used as payload length. That means the actual PDU length will not correspond to the provided fault injection value. Nevertheless, the return value of the function will indicate no error.

Please also note, that a reduction of the PDU data length can lead to signals whose data is not or only partially contained in the PDU payload. Such signals are not interpreted anymore (e.g. in the *Trace* window). If a signal is set whose data is only partially available in the PDU payload, the corresponding data fragment in the PDU is still updated.

## Function Syntax

```plaintext
long ARILFaultInjectionSetPDULength (dbMsg dbMessage, dword len);
```

## Description

Sets a new payload length for the PDU.

## Parameters

- **dbMessage**: The symbolic name of a PDU in the database.
- **len**: New data length.

## Return Values

- **0**: No error.
- **Others**: [Error](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md) in module.

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)