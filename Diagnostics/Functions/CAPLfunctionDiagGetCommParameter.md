[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetCommParameter.md)

# diagGetCommParameter

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagGetCommParameter

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```c
long diagGetCommParameter(char paramName[]); // form 1
long diagGetCommParameter(char paramName[], dword index, char buffer[], dword bufferLen); // form 2
long DiagGetCommParameter(char ecuQualifier[], long isTester, char paramName[]); // form 3
long DiagGetCommParameter(char ecuQualifier[], long isTester, char paramName[], dword index, char buffer[], dword bufferLen); // form 4
```

## Description

Returns the value of a numeric/textual communication parameter of the given or currently active diagnostic description. The values are read from the diagnostic description if they cannot be set in the configuration dialog.

## Parameters

- **qualifier**: The following qualifiers can be used (form 1):
  - **CANoe.AddressMode**: ISO TP address mode:
    - 0: Normal
    - 1: Extended
    - 2: NormalFixed
    - 3: Mixed
    - `< 0`: No ISO TP
  - **CANoe.TxId**: CAN Id for transmitted frames
  - **CANoe.RxId**: CAN Id for received frames
  - **CANoe.BaseAddress**: TP base address
  - **CANoe.EcuAddr**: Number of this node
  - **CANoe.TgtAddr**: Target node number
  - **CANoe.AddrExt**: Address extension byte
  - **CANoe.TxPrio**: Frame transmit priority

Further qualifiers, independent of address mode (form 1):
- **CANoe.UudtId**: If the ECU delivers responses also via UUDT frames, their CAN-Id can be determined here as well.
- **CANoe.Blocksize**: ISO TP parameter, number of consecutive frames between two flow control frames.
- **CANoe.STmin**: ISO TP parameter, minimum interval [ms] between sent consecutive frames, which the sender should maintain.
- **CANoe.FCDelay**: ISO TP parameter, delay of flow control frames sent.

Diagnostics over IP – (form as indicated for each parameter):
- **DoIP.VEHICLE_Adapter**: See [DoIP_SetVehicleAdapter](CAPLfunctionDoIPSetVehicleAdapter.md)
- **DoIP.TESTER_Adapter**: See [DoIP_SetTesterAdapter](CAPLfunctionDoIPSetTesterAdapter.md)
- **DoIP.VEHICLE_Address**: See [DoIP_SetVehicleAddress](CAPLfunctionDoIPSetVehicleAddress.md)
- **DoIP.VEHICLE_LogicalAddress**: Returns the logical DoIP address of the DoIP entity.

K-Line (form 1, all timing parameters in microseconds):
- **KLine.5BaudAddress**: Address sent in the 5 baud wakeup pattern. See [KLine_Set5BaudAddressTester](../../KLine/Functions/CAPLfunctionKLineSet5BaudAddressTester.md)
- **KLine.Baudrate**: Configured baudrate
- **KLine.DataBits**: Number of data bits configured
- **KLine.EcuAddress**: Address of the ECU
- **KLine.ForceLengthByte**: Shall an address byte be sent always? See [KLine_SetHeaderFormat](../../KLine/Functions/CAPLfunctionKLineSetHeaderFormat.md)

- **index**: Set to 0.
- **buffer**: Buffer to retrieve string parameters.
- **bufferLen**: Size of the buffer in bytes.
- **ecuQualifier**: Qualifier of the ECU or target as set in the diagnostic configuration dialog for the respective diagnostic description.
- **isTester**:
  - 0: The node asking for the communication parameter is an ECU simulation
  - 1: The node asking for the communication parameter is a tester
  - other: reserved

## Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md) or value of the parameter.

## Example

You can find examples for this function in the CAPL callback interface (CCI) reference implementations. See [Diagnostics: Connection of the Communication Layer](../CAPLfunctionsDiagnosticsConnectionCommunicationLayer.md) for details.

[Connection of the Communication Layer / Reference Implementations](../CAPLfunctionsDiagnosticsConnectionCommunicationLayer.md) • [Expanded Functions in CAPL](../CAPLfunctionsDiagnosticsExpandedFunctions.md)

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)