# DoIP_SetVehicleAddress

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This function is intended mainly for tester nodes in order to set the target vehicle address. In order to set the IP address for ECU simulation nodes, [DoIP_SetLocalIPAddress](CAPLfunctionDoIPSetLocalIPaddress.md) should be used instead.

The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void DoIP_SetVehicleAddress( char address[]);
```

## Description

Sets the **address** to be used by the DoIP layer. If given, the address is used to access the DoIP entity from the tester equipment, i.e. in case an IP address is used, a Vehicle Identification Request is omitted. In a vehicle simulation it will determine the adapter used for communication; in this case this function must be called in [on preStart](../../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md).

## Parameters

- **address**  
  The address of the DoIP layer. Can be a VIN, IPv4 address, IPv6 address or EID (**Entity ID**, typically a MAC address).  
  **Note**: If an IPv4/IPv6 address is given as **address**, the Vehicle Identification Sequence is omitted.

## Return Values

—

## Example

```plaintext
// Set the vehicle ‘address’
char buffer[256];
DiagGetCommParameter( "DoIP.VEHICLE_Address",
                      0, buffer, elcount( buffer));
DoIP_SetVehicleAddress( buffer);
```

[DiagGetCommParameter](CAPLfunctionDiagGetCommParameter.md) • [DoIP_SetLocalIPaddress](CAPLfunctionDoIPSetLocalIPaddress.md)
