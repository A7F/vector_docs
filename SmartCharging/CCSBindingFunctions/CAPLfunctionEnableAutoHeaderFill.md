[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/CCSBindingFunctions/CAPLfunctionEnableAutoHeaderFill.md)

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [CCS (Communication Setup)](../CAPLFunctionsSmartChargingOverview.md#BMCCS) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#CCSGeneral) » EnableAutoHeaderFill

# EnableAutoHeaderFill

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

MethodReturnValueType EnableAutoHeaderFill (long Enable)

## Description

This function (de-)activates the automatic population of message header with data.

It is available for the **whole** distributed object and for the following embedded members:

- ISO20
- ScheduleRenegotiation
- MeteringConfirmation

The automatic population of message header data is turned **on** by default. Turning it off for the whole distributed object has priority over the embedded members and affects all messages. To turn off for individual embedded members, the automatic population for the whole distributed object must remain enabled.

**Example**

This functionality is also shown in the code provided within the sample configuration [CCS Basic Simulation (Communication Setup)](../../../SampConf/SmartCharging/SCCCSBindingBasicSimulation.md).

**Multimedia Link**

Video tutorial explaining the usage of this method.

**CANoe: ISO 15118-20 CAPL Code | Smart Charging Simulation for BPT**

[Watch on YouTube](https://www.youtube.com/embed/b1On2IeQaHQ?)

## Parameters

- **Enable**: 1 = enable, 0 = disable

## Return Values

**MethodReturnValueType**

All function calls (except for indications) will return a MethodReturnValueType indicating whether the call was successful or not. Possible values:

- 0: OK
- 1: InvalidArgument
- 2: NoMatchingElementFound
- 3: UnknownError

## Example

```plaintext
variables
{
  int AutoFill_header = 0; // Used to re-enable the autofill after sending a message
}

on fct_called EVSE.OnLastReceivedMessageIdChanged
{
  @Common::LastReceivedMessageId = $EVSE.OnLastReceivedMessageIdChanged.LatestCall.lastRxMessageId;
  // Enable AutoHeaderFill if it was previously disabled at the Req/Resp loop
  if (AutoFill_header == 0)
  {
    EVSE.EnableAutoHeaderFill.Call(1);
    AutoFill_header = 1;
  }
}

on value_change EV.SAP.SupportedAppProtocol_Response
{
  int i;
  // Disable AutoHeaderFill for manual definition of the parameter set
  if (AutoFill_header == 1)
  {
    EVSE.EnableAutoHeaderFill.Call(0);
    AutoFill_header = 0;
  }

  // Define custom SessionID to be sent in SessionSetupReq
  for(i=0; i<8;i++)
  {
    $CCS::Simulation::EVSE.ISO20.SessionSetup_Request.Header.SessionID[i] = i;
  }
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
