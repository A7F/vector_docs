[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkConfigDisablePDULayer.md)

**CAPL Functions** » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » ChkConfig_DisablePDULayer

# ChkConfig_DisablePDULayer

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long ChkConfig_DisablePDULayer();
```

## Description

Disables the PDU layer for the current bus context. It affects the next checks that are created after calling this function.

This function has to be used for PDU networks if a check is setup on network level, i.e:

- with a CAN ID
- all Tx/Rx CAN Frames of a node

Default is enabled for a PDU network.

## Parameters

—

## Return Values

- **0**: Successful
- **-1**: Current bus context is not a PDU network.
- **-3**: Test Service Library was not initialized.

## Example

```plaintext
TestCheck c1, c2;
dword bcPduNetwork;

// only needed if the test works on several networks
bcPduNetwork = getBusNameContext("My Pdu Network");
setBusContext(bcPduNetwork);

// always use short header ID
ChkConfig_SetPDUIDFormat(1);

// creates the cycle time check with a PDU header ID
c1 = TestCheck::CreateMsgAbsCycleTimeViolation(2983504, 8, 12);

ChkConfig_DisablePDULayer();
// creates the cycle time check with a CAN ID
c2 = TestCheck::CreateMsgAbsCycleTimeViolation(0x3e1, 8, 12);

// reset to default values
ChkConfig_EnablePDULayer();
ChkConfig_SetPDUIDFormat(0);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
