# EnterChargingSessionPauseOrStandby

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [CCS (Communication Setup)](../CAPLFunctionsSmartChargingOverview.md#BMCCS) » [EV Functions](../CAPLFunctionsSmartChargingOverview.md#CCSGeneral) » EnterChargingSessionPauseOrStandby

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

MethodReturnValueType EnterChargingSessionPauseOrStandby ( )

## Description

Instructs the EV to enter the Charging Session **Pause** or **Standby** procedure. The selected option can be configured using the attribute [PreferStandby](../../../CANoeCANalyzer/SmartCharging/SCISO15118-20/SCISOAttributes.md).

- The **Standby** procedure will be started by sending a Power Delivery Request with ChargeProgress **Standby**. Afterwards, the communication will continue in the respective Charge Loop message pair and can be exited any time using the [ExitStandby](CAPLfunctionExitStandby.md) function (EV) or sending a EVSENotification **ExitStandby** (EVSE).
- The **Pause** procedure will stop the current V2G communication sessions, while also preparing to resume the session once the communication is established again. The session resume procedure can be triggered any time after the Session Stop Request with ChargingSession **Pause** has been accepted by the EVSE and the TCP connection was closed (see callback [TransportLayerDisconnectInd](CAPLfunctionTransportLayerDisconnectInd.md)). First call [StopSimulation](CAPLfunctionStopSimulation.md) and then [StartSimulation](CAPLfunctionStartSimulation.md) to start the communication again.

**Note:** The EVSE may choose to not allow entering the **Standby** procedure, by replying with a **WARNING_StandbyNotAllowed** ResponseCode in the Power Delivery Response message. This will cause the EV to continue charging, behaving as if the method was never called.

## Parameters

—

## Return Values

### MethodReturnValueType

All function calls (except for indications) will return a MethodReturnValueType indicating whether the call was successful or not. Possible values:

- `0`: OK
- `1`: InvalidArgument
- `2`: NoMatchingElementFound
- `3`: UnknownError

## Example

```plaintext
variables
{
  msTimer tRestartAfterPause;
  const long cRestartAfterPauseTimeout = 4000;
  int isEVTriggered = 1;
}

// To be called during ChargeLoop
on key 'x'
{
  if(isEVTriggered == 1)
  {
    // Trigger 'Pause' or 'Standby' via EV
    EV.ISO20.EnterChargingSessionPauseOrStandby.Call();
  }
  else
  {
    // Trigger 'Pause' or 'Standby' via EVSE
    EVSE.SetNextEVSENotification.Call(_CCS::DataTypes::EVSENotificationType::Pause);
  }
}

// To be called during 'Standby' procedure
on key 'c'
{
  if(isEVTriggered == 1)
  {
    // Exit 'Standby' via EV
    EV.ISO20.ExitStandby.Call();
  }
  else
  {
    // Exit 'Standby' via EVSE
    EVSE.SetNextEVSENotification.Call(_CCS::DataTypes::EVSENotificationType::ExitStandby);
  }
}

on fct_returning EV.TransportLayerDisconnectInd
{
  // Execute 'Pause' logic, if it was requested and accepted
  if($EV.ISO20.SessionStop_Request.ChargingSession == _CCS::DataTypes::parISO20ChargingSessionType::Pause
      && $EV.ISO20.SessionStop_Response.ResponseCode == _CCS::DataTypes::ISO20ResponseCodeType::OK)
  {
    setTimer(tRestartAfterPause, cRestartAfterPauseTimeout);
    EV.StopSimulation.Call();
    EVSE.StopSimulation.Call();
  }
}

on timer tRestartAfterPause
{
// Skip SLAC after pause
setAttribute(CCS::Simulation::EV, CCSBinding::EV::SLACCommunication, CCSBinding::Disabled);
  // Restart communication
  EV.StartSimulation.Call();
  EVSE.StartSimulation.Call();
}
```

[ExitStandby](CAPLfunctionExitStandby.md)
