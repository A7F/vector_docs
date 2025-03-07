[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Functions/CAPLfunctionCanGetTransceiverErrorCount.md)

**CAPL Functions** » **CAN** » **canGetTransceiverErrorCount**

# canGetTransceiverErrorCount

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long canGetTransceiverErrorCount(long channel);
```

## Description

Gets the total count of transceiver errors of a CAN channel.

## Parameters

- **channel**: CAN channel (1…32).

## Return Values

Total count of transceiver errors, if CAN statistics is enabled; 0 otherwise.

## Example

```plaintext
write("Transceiver errors on CAN1: %i", canGetTransceiverErrorCount(1));
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)