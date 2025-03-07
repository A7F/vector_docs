[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPSelectVehicle.md)

**CAPL Functions** » **Diagnostics** » **DoIP_SelectVehicle**

# DoIP_SelectVehicle

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
These functions only work if the tester program uses the built-in DoIP channels, i.e. they do not work if the tester program uses the [CAPL Callback Interface (CCI)](../CAPLfunctionsDiagnosticsConnectionCommunicationLayer.md).

## Function Syntax

```plaintext
long DoIP_SelectVehicle(byte EID[6]);
long DoIP_SelectVehicle(char VIN[]);
```

## Description

Specify which vehicle the tester shall target, i.e. indicate in the Vehicle Identification Request Message, or select one of the responding vehicles for communication.

- If this function is called before a Vehicle Identification Request (VIR) Message is sent, it will set the Vehicle Identification Number (VIN) or Entity ID (EID) in the VIR messages.
- If this function is called during a vehicle identification phase, a matching vehicle will be selected if its Vehicle Identification Response (or Announcement Message, VAM) has been received. It is possible to call this function from the [DoIP_VehicleIdentificationCompleteInd](CAPLfunctionDoIPVehicleIdentificationCompleteInd.md) callback.

To set the VIN and EID in an ECU simulation use the DoIP.DLL functions [DoIP_SetEID](CAPLfunctionDoIPSetEID.md) and [DoIP_SetVIN](CAPLfunctionDoIPSetEID.md).

## Parameters

- **EID**: (6 bytes) entity ID, typically an Ethernet MAC address.
- **VIN**: The vehicle identification number (17 characters). If an empty string is given, VIR messages without parameter are sent.

## Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

```plaintext
TestCase TC_AccessVehicle1
{
  diagRequest ReadEcuInfo req;

  DiagSetTarget( "ECU1"); // a DoIP description

  // --- start VIR targeting a specific vehicle via its VIN

  DoIP_SelectVehicle( "VECT0RVEH1CLE0123");

  req.SendRequest();
  // A VIR with VIN should be responded quite fast
  TestWaitForDiagResponse( req, 1000);

  diagCloseChannel(); // make sure that another VIR will be sent

  // --- send VIR without indicating a vehicle

  DoIP_SelectVehicle( ""); // no-parameter-VIR-message

  req.SendRequest();
  // A VIR without parameter may take a long time, including repeats
  TestWaitForDiagResponse( req, 9000);

  diagCloseChannel();
}
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)