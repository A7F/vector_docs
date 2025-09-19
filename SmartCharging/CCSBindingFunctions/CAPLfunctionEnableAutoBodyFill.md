[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/CCSBindingFunctions/CAPLfunctionEnableAutoBodyFill.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [CCS (Communication Setup)](../CAPLFunctionsSmartChargingOverview.md#BMCCS) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#CCSGeneral) » EnableAutoBodyFill

# EnableAutoBodyFill

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

MethodReturnValueType EnableAutoBodyFill (long Enable)

## Description

This function (de-)activates the automatic population of message bodies with data.

It is available for the **whole** distributed object and for the following embedded members:

- ISO20
- ScheduleRenegotiation
- MeteringConfirmation

The automatic population of message body data is turned **on** by default. Turning it off for the whole distributed object has priority over the embedded members and affects all messages. To turn off for individual embedded members, the automatic population for the whole distributed object must remain enabled.

### Example

This functionality is also shown in the code provided within the sample configuration [CCS Basic Simulation (Communication Setup)](../../../SampConf/SmartCharging/SCCCSBindingBasicSimulation.md).

### Multimedia Link

Video tutorial explaining the usage of this method.

**CANoe: ISO 15118-20 CAPL Code | Smart Charging Simulation for BPT**

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
  int AutoFill_body = 0; // Used to re-enable the autofill after sending a message
}

on fct_called EVSE.OnLastReceivedMessageIdChanged
{
  @Common::LastReceivedMessageId = $EVSE.OnLastReceivedMessageIdChanged.LatestCall.lastRxMessageId;
  // Enable AutoBodyFill if it was previously disabled at the Req/Resp loop
  if (AutoFill_body == 0)
  {
    EVSE.EnableAutoBodyFill.Call(1);
    AutoFill_body = 1;
  }
}

on value_change EVSE.ISO20.ServiceDetail_Request
{
  if(IsEVSERolePassive())
    return;

  FUNC_Set_ServiceDetailRes();
}

void FUNC_Set_ServiceDetailRes()
{
  // Selection of ServiceID (e.g. DC_BPT)
  if ($EVSE.ISO20.ServiceDetail_Request.ServiceID == 6)
  {
    // Disable AutoBodyFill for manual definition of the parameter set
    if (AutoFill_body == 1)
    {
      EVSE.EnableAutoBodyFill.Call(0);
      AutoFill_body = 0;
    }

    // Definition of required service ID (shall be equal to the if query)
    $EVSE.ISO20.ServiceDetail_Response.ServiceID = $EVSE.ISO20.ServiceDetail_Request.ServiceID;

    _ServiceDetail_PrepareResponseContent_DC_BPT_List();
  }
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
