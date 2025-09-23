[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCOnGenericVSHostActionInd.md)

# OnGenericVSHostActionInd

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [CCS (Communication Setup)](../CAPLFunctionsSmartChargingOverview.md#BMCCS) » [Shared Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CCSCallback) » OnGenericVSHostActionInd

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void OnGenericVSHostActionInd( byte oui [], LinkStatusType linkStatus);
```

## Description

The callback is called as soon as a VS_Host_Action.Ind or equivalent message is received. The interpretation of the message depends on the vendor OUI and will then be mapped to the respective link status values.

Currently supported OUIs:

- Qualcomm (0x00B052)
- MStar, MediaTek and Vertexcom (0x0013D7)
- Lumissil (0x0016E8)

It is available for the whole Distributed Object.

## Parameters

- **oui**: The OUI of the received host action indication.
- **linkStatus**: The link status that was indicated by the received message:
  - 0: Disconnected
  - 1: ReadyToJoin
  - 2: Connected
  - 3: Undefined

## Return Values

—

## Example

—
