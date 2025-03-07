# K-Line CAPL Functions

[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/KLine/CAPLfunctionsKLineOverview.md)

[CAPL Functions](../CAPLfunctions.md) » K-Line CAPL Functions

Valid for:  CANoe DE

## ON THIS PAGE:

- [Callbacks](#Callbacks)
- [Configuring and Controlling a K-Line ECU Simulation](#APIsConfiguringControllingKLineECUSimulation)
- [Configuring and Controlling a K-Line Tester](#APIsConfiguringControllingKLineTester)
- [Controlling a Diagnostic Channel](#APIsControllingDiagnosticsChannel)
- [Test Feature Set for K-Line](#TestFeatureSetKLine)

---

## Callbacks [▲ back](#Shortcuts)

| Functions                                                                 | Short Description                                      |
|---------------------------------------------------------------------------|--------------------------------------------------------|
| [_Diag_ChannelStateChanged](../Diagnostics/Functions/CAPLfunctionDiagChannelStateChanged.md) | Indicates the state of the diagnostic channel.         |
| [_Diag_PreSend](Functions/CAPLfunctionDiagPreSend.md)                    | Is called before a frame is transmitted.               |
| [_KLine_ByteReceptionInd](Functions/CAPLfunctionKLineByteReceptionInd.md) | Is called when a byte has been received.               |
| [_KLine_ByteTransmissionCon](Functions/CAPLfunctionKLineByteTransmissionCon.md) | Is called when a byte has been transmitted.            |
| [_KLine_DataCon](Functions/CAPLfunctionKLineDataCon.md)                  | Called for a transmitted K-Line response.              |
| [_KLine_DataInd](Functions/CAPLfunctionKLineDataInd.md)                  | Called for a received K-Line request.                  |
| [_KLine_ErrorInd](Functions/CAPLfunctionKLineErrorInd.md)                | Called when a protocol error occurred.                 |
| [_KLine_FastInitPatternReceived](Functions/CAPLfunctionKLineFastInitPatternReceived.md) | Called when a fast init pattern has been received.     |
| [_KLine_FrameReceptionInd](Functions/CAPLfunctionKLineFrameReceptionInd.md) | Is called when a frame has been received.              |
| [_KLine_FrameTransmissionCon](Functions/CAPLfunctionKLineFrameTransmissionCon.md) | Is called when a frame has been transmitted.           |

## Configuring and Controlling a K-Line ECU Simulation [▲ back](#Shortcuts)

| Functions                                                                 | Short Description                                      |
|---------------------------------------------------------------------------|--------------------------------------------------------|
| [DiagInitEcuSimulation](Functions/CAPLfunctionDiagInitEcuSimulation.md)  | Initialize CAPL node to represent a diagnostics ECU simulation. |
| [DiagSendResponsePDU](Functions/CAPLfunctionDiagSendResponsePDU.md)      | Sends a raw byte buffer.                               |
| [KLine_CreateECURepresentation](Functions/CAPLfunctionKLineCreateECURepresentation.md) | Initialize K-Line ECU communication on given channel.  |
| [KLine_Init5BaudEcuParams](Functions/CAPLfunctionKLineInit5BaudEcuParams.md) | Initialize K-Line channel for reception of the 5 baud pattern. |
| [KLine_ResetECUConnection](Functions/CAPLfunctionKLineResetECUConnection.md) | Resets the connection state of the simulated ECU.      |
| [KLine_SendFrame](Functions/CAPLfunctionKLineSendFrame.md)               | Send data on the active K-Line communication channel.  |
| [KLine_SetP1ECU](Functions/CAPLfunctionKLineSetP1ECU.md)                 | Sets the interbyte time of a response.                 |
| [KLine_SetP2max](Functions/CAPLfunctionKLineSetP2max.md)                 | Sets the maximum time between the client request and the server response, or between 2 server responses. |
| [KLine_SetP3max](Functions/CAPLfunctionKLineSetP3max.md)                 | Sets the maximum time between the end of the server response and start of a new client request. |

## Configuring and Controlling a K-Line Tester [▲ back](#Shortcuts)

| Functions                                                                 | Short Description                                      |
|---------------------------------------------------------------------------|--------------------------------------------------------|
| [DiagSendRequestPDU](Functions/CAPLfunctionDiagSendRequestPDU.md)        | Sends a raw byte buffer.                               |
| [KLine_EnableSegmentedResponses](Functions/CAPLfunctionKLineEnableSegmentedResponses.md) | Enables receiving segmented responses.                 |
| [KLine_GetMeasuredInitParameter](Functions/CAPLfunctionKLineGetMeasuredInitParameter.md) | Retrieves the different parameters of the init patterns. |
| [KLine_Set5BaudAddressTester](Functions/CAPLfunctionKLineSet5BaudAddressTester.md) | Sets the 5 baud address for the 5 baud init pattern.   |
| [KLine_SetBaudrate](Functions/CAPLfunctionKLineSetBaudrate.md)           | Allows changing the baudrate during the measurement.   |
| [KLine_SetECUAddress](Functions/CAPLfunctionKLineSetECUAddress.md)       | Sets the address of the ECU.                           |
| [KLine_SetFunctionalAddress](Functions/CAPLfunctionKLineSetFunctionalAddress.md) | Sets the functional address of the ECU.                |
| [KLine_SetHeaderFormat](Functions/CAPLfunctionKLineSetHeaderFormat.md)   | Configures the used header format.                     |
| [KLine_SetInitType](Functions/CAPLfunctionKLineSetInitType.md)           | Configures the used initialization pattern.            |
| [KLine_SetP3Tester](Functions/CAPLfunctionKLineSetP3Tester.md)           | Sets the P3 time which the tester waits until transmitting a further request. |
| [KLine_SetP4Tester](Functions/CAPLfunctionKLineSetP4Tester.md)           | Sets the interbyte time of a request.                  |
| [KLine_SetTesterAddress](Functions/CAPLfunctionKLineSetTesterAddress.md) | Sets the address of the tester.                        |
| [KLine_SetUARTParameter](Functions/CAPLfunctionKLineSetUARTParameter.md) | Configures the way bytes are sent on K-Line.           |
| [KLine_SetW4Tester](Functions/CAPLfunctionKLineSetW4Tester.md)           | Sets the W4 timing of the tester between keybyte2 and keybyte2Not. |
| [KLine_SetW5Tester](Functions/CAPLfunctionKLineSetW5Tester.md)           | Sets the W5 timing before the tester starts to transmit the address byte. |
| [KLine_SetWakeUpTimesTester](Functions/CAPLfunctionKLineSetWakeUpTimesTester.md) | Sets the timings of the fast init wake-up pattern.     |
| [KLine_SuppressAutomaticStopCommunication](Functions/CAPLfunctionKLineSuppressAutomaticStopCommunication.md) | For a fast init ECU, automatic sending of a Stop communication command will be suppressed after closing the channel or a S3 timeout. |
| [KLine_UseDefaultHeader](Functions/CAPLfunctionKLineUseDefaultHeader.md) | The header format specified in the diagnostic description file will be used. |

## Controlling a Diagnostic Channel [▲ back](#Shortcuts)

These functions are not restricted to K-Line only.

| Functions                                                                 | Short Description                                      |
|---------------------------------------------------------------------------|--------------------------------------------------------|
| [DiagCloseChannel](../Diagnostics/Functions/CAPLfunctionDiagCloseChannel.md) | Closes a channel.                                      |
| [DiagConnectChannel](../Diagnostics/Functions/CAPLfunctionDiagConnectChannel.md) | Connects a channel.                                    |
| [DiagDisconnectChannel](../Diagnostics/Functions/CAPLfunctionDiagDisconnectChannel.md) | Disconnects a channel.                                 |
| [DiagIsChannelConnected](../Diagnostics/Functions/CAPLfunctionDiagIsChannelConnected.md) | Checks if a channel is already in state **Connected**. |

## Test Feature Set for K-Line [▲ back](#Shortcuts)

| Functions                                                                 | Short Description                                      |
|---------------------------------------------------------------------------|--------------------------------------------------------|
| [TestGetWaitEventKLineByte](../Test/Functions/CAPLfunctionTestGetWaitEventKLineByte.md) | If a byte is the last event that triggers a wait instruction, the content can be called up with this function. |
| [TestGetWaitEventKLineFrame](../Test/Functions/CAPLfunctionTestGetWaitEventKLineFrame.md) | If a K-Line frame is the last event that triggers a wait instruction, the content can be called up with this function. |
| [TestWaitForDiagChannelClosed](../Test/Functions/CAPLfunctionTestWaitForDiagChannelClosed.md) | Waits for the occurrence of the state change of a diagnostic channel to the state **Closed**. |
| [TestWaitForDiagChannelConnected](../Test/Functions/CAPLfunctionTestWaitForDiagChannelConnected.md) | Waits for the occurrence of the state change of a diagnostic channel to the state **Connected**. |
| [TestWaitForDiagKLineByteReceived](../Test/Functions/CAPLfunctionTestWaitForDiagKLineByteReceived.md) | Waits for the occurrence of a received byte.           |
| [TestWaitForDiagKLineByteTransmitted](../Test/Functions/CAPLfunctionTestWaitForDiagKLineByteTransmitted.md) | Waits for the occurrence of a transmitted byte.        |
| [TestWaitForDiagKLineFrameReceived](../Test/Functions/CAPLfunctionTestWaitForDiagKLineFrameReceived.md) | Waits for the occurrence of a received valid message.  |
| [TestWaitForDiagKLineFrameTransmitted](../Test/Functions/CAPLfunctionTestWaitForDiagKLineFrameTransmitted.md) | Waits for the occurrence of a transmitted valid message. |

---

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)