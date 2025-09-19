[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimGetProperty.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_TIMGetProperty

# Iso11783IL_TIMGetProperty

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_TIMGetProperty(char propertyName[]); // form 1
long Iso11783IL_TIMGetProperty(dbNode participant, char propertyName[]); // form 2
```

## Description

Gets a property of the TIM server/client.

## Parameters

- **propertyName**: Name of the property.
  - **Properties**: `isServerMaster`
    - **Value Range**: 0..1
    - **Description**:
      - 1: TIM server is TIM server master.
      - 0: TIM server is no TIM server master.
  - **Properties**: `bootTime`
    - **Value Range**: 0..255 [seconds]
    - **Description**: Boot time which is reported in the TIM_ServerVersionResponse message.
  - **Properties**: `minimumVersion`
    - **Value Range**: 0..255
    - **Description**: Minimum TIM version number of the TIM client/server.
  - **Properties**: `implementedVersion`
    - **Value Range**: 0..255
    - **Description**: Implemented TIM version number of the TIM client/server.
  - **Properties**: `deactivateCertificateValidation`
    - **Value Range**: 0..FFh
    - **Description**:
      - Bit 0 = 1: Validation of Conformance Certification information against device certificate is deactivated.
      - Bit 1 = 1: Validation of ISOBUS device name (NAME) against device certificate is deactivated.
      - Bit 2 = 1: Validation of function capabilities against the certificates is deactivated.
      - Bit 3 = 1: Check for revoked certificates is deactivated.
      - Bit 4 = 1: Check for certificate type (client or server certificate) is deactivated.
  - **Properties**: `enableDemoMode`
    - **Value Range**: 0..1
    - **Description**:
      - 1: Demo mode is enabled. Therefore no certificates and keys are validated.
      - 0: Demo mode is disabled.
  - **Properties**: `useRequestCounter`
    - **Value Range**: 0..1
    - **Description**:
      - 1: Increment request counter (starting with 0) in function request messages.
      - 0: Request counter is not used when function request messages are sent.
  - **Properties**: `restartAfterWorkflowViolation`
    - **Value Range**: 0..1
    - **Description**:
      - 1: Client restarts communication to the server if there is a workflow violation.
      - 0: Client does not restart communication to the server if there is a workflow violation.
  - **Properties**: `requireAcknowledgeOfStartOfMotion`
    - **Value Range**: 0..1
    - **Description**:
      - 1: Operator acknowledgment ([Iso11783IL_TIMOperatorAcknowledgeStartOfMotion](CAPLfunctionIso11783ILtimOperatorAcknowledgeStartOfMotion.md)) is necessary to start vehicle motion by the client.
      - 0: Client can start vehicle motion without operator acknowledgment.

- **participant**: TIM participant (TIM server or TIM client).

## Return Values

- **≥ 0**: Value
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

[Iso11783IL_TIMSetProperty](CAPLfunctionIso11783ILtimSetProperty.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
