# DoIP_SetGatewayLogicalAddress

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void DoIP_SetGatewayLogicalAddress(dword logicalAddress);
```

## Description

Sets the logical address of the gateway that responds to a vehicle announcement request.

## Parameters

- **logicalAddress**
  - 0: there is no gateway or gateway’s and target’s logical address are identical
  - 1..65535: the gateway has the given logical address
  - other: reserved

## Return Values

—

## Example

```plaintext
DoIP_SetVehicleLogicalAddress( 0x201);
DoIP_SetGatewayLogicalAddress( 0x100);
DoIP_ConnectToVehicle();
// if the gateway with logical address 0x0100 responds to the vehicle
// identification request, the connection can be made even though the ECU
// with logical address 0x0201 is the target of the communication
```

[DoIP_SetVehicleLogicalAddress](CAPLfunctionDoIPSetVehicleLogicalAddress.md)
