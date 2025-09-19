# CarMaker CAPL Functions

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE

CarMaker

- Only available with CarMaker Interface & CANoe DE product.
- Via the CarMaker interface it is possible to start single tests or test series in CarMaker and monitor selected simulation data. The control and stimulation of the CarMaker test runs is done via the APO interface provided by CarMaker. This can be called from your CANoe DE product using special [CAPL functions](#).
- This component is included in the setup of your CANoe DE product. In the setup folder **Installer Additional Components** you find the corresponding setup files.

---

### Functions

- [CarMaker_BeginWrite, CarMaker_FinishWrite](Functions/CAPLfunctionCarMakerBeginFinishWrite.md)
  - Groups several write operations to a single atomic write operation.

- [CarMaker_Connect](Functions/CAPLfunctionCarMakerConnect.md)
  - Creates a connection to the CarMaker instance running on the selected host by the given user.

- [CarMaker_Disconnect](Functions/CAPLfunctionCarMakerDisconnect.md)
  - Terminates the connection to CarMaker.

- [CarMaker_GetNamedValue](Functions/CAPLfunctionCarMakerGetNamedValue.md)
  - Copies the current value with the given name into the buffer provided by the caller.

- [CarMaker_InvokeCommand](Functions/CAPLfunctionCarMakerInvokeCommand.md)
  - Synchronously calls a generic command and stores the result.

- [CarMaker_LoadTestRun](Functions/CAPLfunctionCarMakerLoadTestRun.md)
  - Loads a test run with the given name within CarMaker.

- [CarMaker_LoadTestSeries](Functions/CAPLfunctionCarMakerLoadTestSeries.md)
  - Loads a test series with the given name within CarMaker.

- [CarMaker_Poll](Functions/CAPLfunctionCarMakerPoll.md)
  - Manages the internal state and updates the CANoe system variables.

- [CarMaker_SetNamedValue](Functions/CAPLfunctionCarMakerSetNamedValue.md)
  - Defines or changes a named value in CarMaker.

- [CarMaker_StartCommand](Functions/CAPLfunctionCarMakerStartCommand.md)
  - Asynchronously calls a generic command and ignores the result.

- [CarMaker_StartSim](Functions/CAPLfunctionCarMakerStartSim.md)
  - Starts the simulation in CarMaker.

- [CarMaker_StartTestSeries](Functions/CAPLfunctionCarMakerStartTestSeries.md)
  - Starts test series asynchronously in CarMaker.

- [CarMaker_Status](Functions/CAPLfunctionCarMakerStatus.md)
  - Retrieves the status of the CarMaker connection.

- [CarMaker_StatusText](Functions/CAPLfunctionCarMakerStatusText.md)
  - Retrieves a textual representation of the current state.

- [CarMaker_StopSim](Functions/CAPLfunctionCarMakerStopSim.md)
  - Stops the simulation in CarMaker.

- [CarMaker_StopTestSeries](Functions/CAPLfunctionCarMakerStopTestSeries.md)
  - Stops test series immediately in CarMaker.

- [CarMaker_Subscribe](Functions/CAPLfunctionCarMakerSubscribe.md)
  - Subscribes a group of CarMaker quantities as CANoe system variables.

- [CarMaker_SubscribeMs](Functions/CAPLfunctionCarMakerSubscribeMs.md)
  - Subscribes a group of CarMaker quantities as CANoe system variables.

- [CarMaker_WriteAbs](Functions/CAPLfunctionCarMakerWriteAbs.md)
  - Modifies the value of a CarMaker quantity.

[Return Codes](CAPLfunctionsCarMakerReturnCodes.md) • [CarMaker Interface: Overview](../../CANoeCANalyzer/Interfaces/CarMaker/CarMaker.md)
