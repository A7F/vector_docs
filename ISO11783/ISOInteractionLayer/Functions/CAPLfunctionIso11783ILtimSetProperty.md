[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimSetProperty.md)

# Iso11783IL_TIMSetProperty

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_TIMSetProperty

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_TIMSetProperty(char propertyName[], long value); // form 1
long Iso11783IL_TIMSetProperty(dbNode participant, char propertyName[], long value); // form 2
```

## Description

Sets a property of the TIM server/client.

## Parameters

- **propertyName**: Name of the property.
  - **isServerMaster**:
    - Value Range: 0..1
    - Default value server: 0
    - Default value client: —
    - Description:
      - 1: TIM server is TIM server master.
      - 0: TIM server is no TIM server master.
  - **bootTime**:
    - Value Range: 0..255 [seconds]
    - Default value server: 1
    - Default value client: —
    - Description: Boot time which is reported in the TIM_ServerVersionResponse message.
  - **minimumVersion**:
    - Value Range: 0..255
    - Default value server: 0
    - Default value client: 0
    - Description: Minimum TIM version number of the TIM client/server.
  - **implementedVersion**:
    - Value Range: 0..255
    - Default value server: 0
    - Default value client: 0
    - Description: Implemented TIM version number of the TIM client/server.
  - **deactivateCertificateValidation**:
    - Value Range: 0..FFh
    - Default value server: 0
    - Default value client: 0
    - Description:
      - Bit 0 = 1: Validation of Conformance Certification information against device certificate is deactivated.
      - Bit 1 = 1: Validation of ISOBUS device name (NAME) against device certificate is deactivated.
      - Bit 2 = 1: Validation of function capabilities against the certificates is deactivated.
      - Bit 3 = 1: Check for revoked certificates is deactivated.
      - Bit 4 = 1: Check for certificate type (client or server certificate) is deactivated.
  - **enableDemoMode**:
    - Value Range: 0..1
    - Default value server: 0
    - Default value client: 0
    - Description:
      - 1: Demo mode is enabled. Therefore no certificates and keys are validated.
      - 0: Demo mode is disabled.
  - **useRequestCounter**:
    - Value Range: 0..1
    - Default value server: 0
    - Default value client: 0
    - Description:
      - 1: Increment request counter (starting with 0) in function request messages.
      - 0: Request counter is not used when function request messages are sent.
  - **restartAfterWorkflowViolation**:
    - Value Range: 0..1
    - Default value server: —
    - Default value client: 0
    - Description:
      - 1: Client restarts communication to the server if there is a workflow violation.
      - 0: Client does not restart communication to the server if there is a workflow violation.
  - **requireAcknowledgeOfStartOfMotion**:
    - Value Range: 0..1
    - Default value server: 0
    - Default value client: —
    - Description:
      - 1: Operator acknowledgment ([Iso11783IL_TIMOperatorAcknowledgeStartOfMotion](CAPLfunctionIso11783ILtimOperatorAcknowledgeStartOfMotion.md)) is necessary to start vehicle motion by the client.
      - 0: Client can start vehicle motion without operator acknowledgment.
  - **minimumAuthVersion**:
    - Value Range: 2..250, 255
    - Default value server: 255
    - Default value client: 255
    - Description:
      - 2..250: Minimum Authentication Version supported by the TIM client/server.
      - 255: Authentication Version is not supported by the TIM client/server.
      - If both versions (minimum and implemented) are set to 255 then the TIM client/server does not know/support the Authentication Version mechanism.
  - **implementedAuthVersion**:
    - Value Range: 1..250, 255
    - Default value server: 255
    - Default value client: 255
    - Description:
      - 1..250: Implemented Authentication Version supported by the TIM client/server.
      - 255: Authentication Version is supported by the TIM client/server.
      - If Implemented Authentication Version is between 2 and 250 an **Auth_ServerVersionRequest** or **Auth_ClientVersionRequest** message is responded by the TIM server or TIM client.
      - If both versions (minimum and implemented) are set to 255 then the TIM client/server does not know/support the Authentication Version mechanism.

- **value**: New value of the property.

- **participant**: TIM participant (TIM server or TIM client).

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

[Iso11783IL_TIMGetProperty](CAPLfunctionIso11783ILtimGetProperty.md)

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
