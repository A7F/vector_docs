[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPMessageAcknowledgeInd.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » _DoIP_MessageAcknowledgeInd

# _DoIP_MessageAcknowledgeInd

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void _DoIP_MessageAcknowledgeInd( WORD payloadType, long ackCode, WORD testerAddress, WORD ecuAddress);
```

## Description

A positive or negative acknowledgment was received in the tester. The code may provide additional information on the reason for a negative acknowledge.

## Parameters

- **payloadType**
  - **ISO13400**
    - 0x8002: Diagnostic message positive acknowledgment
    - 0x8003: Diagnostic message negative acknowledgment
  - **HSFZ**
    - 0x02: positive acknowledgment
    - 0x40..0xFF: negative acknowledgment (different reasons)
    - other reserved

- **ackCode**
  - Response code transported in the acknowledgment, or -1 for HSFZ.
    - -1: not available, i.e. HSFZ does not send a code
    - 0: OK (ISO 13400 positive acknowledgment)
    - 2..8: Not OK (ISO 13400 negative acknowledgment)
    - other reserved

- **testerAddress**
  - Logical address of the tester the acknowledgment is directed to.

- **ecuAddress**
  - Logical address of the entity that sends the acknowledgment.

## Return Values

—

## Example

```plaintext
void _DoIP_MessageAcknowledgeInd( word payloadType, long code, word testerAddress, word ecuAddress)
{
  write( "_DoIP_MessageAcknowledgeInd type %04x, %d, tester=%04x, ecu=%04x", payloadType, code, testerAddress, ecuAddress);
}
```

[DoIP_SetNextDiagnosticMessageNACKCode](CAPLfunctionDoIPSetNextDiagnosticMessageNACKCode.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)