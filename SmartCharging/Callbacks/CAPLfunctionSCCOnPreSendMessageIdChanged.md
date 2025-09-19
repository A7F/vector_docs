[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCOnPreSendMessageIdChanged.md)

**CAPL Functions** » **Smart Charging** » **CCS (Communication Setup)** » **Shared Callback Functions** » **OnPreSendMessageIdChanged**

# OnPreSendMessageIdChanged

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void OnPreSendMessageIdChanged ( LastTxMessageIdType txMessageId )
```

## Description

This callback is called before a message is sent. Using the active simulation, the individual values of the corresponding message can be changed here. This includes message parameters with meaningful values that were set by the state machine before sending. For correct usage refer to the CAPL example.

It is available for the **whole** Distributed Object.

## Parameters

- **txMessageId**: ID of the message that will be sent. See [MessageIDs](SCC_MessageID.md) for more information.

## Return Values

—

## Example

Example to send a valid **AuthorizationSetup_Response** message with a failed response code:

```plaintext
on value_change EVSE.OnPreSendMessageIdChanged.LatestCall.txMessageId
{
  if($this == _CCS::DataTypes::MessageIdType::AuthorizationSetupRes)
  {
    $EVSE.ISO20.AuthorizationSetup_Response.ResponseCode = _CCS::DataTypes::ISO20ResponseCodeType::FAILED;
  }
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
