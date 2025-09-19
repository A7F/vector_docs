# diagGetCommParameter (FlexRay)

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagGetCommParameterFR.md)

**CAPL Functions** » **Diagnostics** » diagGetCommParameter (FlexRay)

---

**Valid for**: CANoe DE

---

**Note**: Only available with Option .FlexRay!

## Function Syntax

```plaintext
long diagGetCommParameter (char qualifier[]);
```

## Description

Returns the value of a numeric/textual communication parameter of the given or currently active diagnostic description. The values are read from the diagnostic description if they cannot be set in the configuration dialog.

## Parameters

- **qualifier**: Parameters for diagnostics on FlexRay. See [diagGetCommParameter](CAPLfunctionDiagGetCommParameter.md) for parameters that are not FlexRay specific.

### Qualifiers

- **FlexRay.Protocol**: The protocol variant to use.
  - 0: AUTOSAR 2.x
  - rest: reserved for future extensions

- **FlexRay.AddressType**: Using one or two byte addresses?
  - 1: One byte addresses
  - 2: Two byte addresses

- **FlexRay.LocalAddress**: Address of *this* node, i.e. ECU address in ECU simulation, tester address in tester nodes.

- **FlexRay.RemoteAddress**: Address of the target node, i.e. ECU address in tester nodes, tester address in ECU simulation.

- **FlexRay.ConnectionMode**: Control the usage of flow control frames.
  - 1: Unicast
  - 2: Acknowledged Unicast
  - 3: Acknowledged Unicast with Retry
  - rest: reserved

  **Note**: Please refer to the AUTOSAR FlexRay TP specification for details on the parameter value semantics.

- **FlexRay.MessageLength**: Control the TP PDU types used.
  - 1: ISO
  - 2: ISO6
  - 3: L16M
  - 4: L4G
  - rest: reserved

  **Note**: Please refer to the AUTOSAR FlexRay TP specification for details on the parameter value semantics.

- **FlexRay.StMin**: Separation time [ms]

  **Note**: Please refer to the AUTOSAR FlexRay TP specification for details on the parameter value semantics.

- **FlexRay.BlockSize**: Block size

  **Note**: Please refer to the AUTOSAR FlexRay TP specification for details on the parameter value semantics.

### Configuration of send and receive slots/PDUs

- **FlexRay.LocalStartSlot**: Id of first slot the node sends in
- **FlexRay.LocalCount**: Number of consecutive slots to send in
- **FlexRay.LocalStartCycle**: First cycle to send slots in
- **FlexRay.LocalCycleRepetition**: Cycle spacing to send slots in
- **FlexRay.LocalPayloadLen**: Length of slots to send in

- **FlexRay.RemoteStartSlot**: Id of first slot to receive
- **FlexRay.RemoteCount**: Number of consecutive slots to receive
- **FlexRay.RemoteStartCycle**: First cycle to receive slots in
- **FlexRay.RemoteCycleRepetition**: Cycle spacing of slots to receive
- **FlexRay.RemotePayloadLen**: Length of slots received

## Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

**Example**: You can find examples for this function in the CAPL callback interface (CCI) reference implementations. See [Diagnostics: Connection of the Communication Layer](../CAPLfunctionsDiagnosticsConnectionCommunicationLayer.md) for details.

---
