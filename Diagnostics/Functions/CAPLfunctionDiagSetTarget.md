# diagSetTarget

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long diagSetTarget (char ecuName[])
```

## Description

Sets the target ECU with which the tester shall communicate from now on and configures/establishes the communication channel to that ECU.

**Note**

- This function cannot be used in the on prestart handler, is only to be used inside a CAPL tester node and must not be called from inside a CAPL ECU node which simulates diagnostics.
- In case you are implementing a diagnostic ECU simulator node, assign the diagnostic description to the node by selecting the ECU’s name in the **Function/Node** combo box of the **Diagnostics configuration** dialog / **Assignments** tab.
- Instead of assigning a simulation node in the configuration dialog, you may alternatively use the function [DiagInitECUSimulation](../../KLine/Functions/CAPLfunctionDiagInitEcuSimulation.md) to establish a link between your CAPL code and the corresponding diagnostic description.

After calling the function in the tester, the following actions are executed:

- From now on the tester will interpret and use all diagnostic objects in the CAPL code of this node as defined in the respective diagnostic description file.
- From now on the tester will use the SeedKey DLL defined for this target in the diagnostic configuration dialog when computing a security key with [diagGenerateKeyFromSeed()](CAPLfunctionDiagGenerateKeyFromSeed.md).
- All diagnostic objects (requests/responses) defined in the CAPL code are re-initialized for the given target. If DiagSetTarget() was called for the same or a different target before, the request/response objects will no longer keep modifications made in a previous session with a previous target ECU.
- DiagSetTarget shall not be called in the "on preStart" handler of a test module, since it would be called only once when the measurement starts. It is recommended to call it in the "**preparation**" phase of an XML test module, or to make sure programmatically that it is called before any test case using diagnostics is executed.
- The communication layer is configured:
  - In case of a CAPL Callback interface (CCI) being used, the function [_Diag_SetChannelParameters](CAPLfunctionDiagSetChannelParameters.md) is called to configure the parameters of the underlying TP modeling library.
  - If no CCI is implemented, a built-in diagnostic channel is configured according to the network type to which the diagnostic description is attached and according to the communication parameters of the selected diagnostic interface. For connection oriented transport protocols (like e.g. VW TP 2.0) furthermore not only the parameters of the connection are configured, but a communication channel is actually established between tester and ECU.

## Parameters

- **ecuName**: Qualifier of the ECU as set in the diagnostic configuration dialog for the respective diagnostic description (CDD/ODX).

## Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

```c
// In this example, diagSetTarget(<ECU>) is simply called once in the
// ‘MainTest’ function of a test node, as this tester only needs to access
// one dedicated ECU with ECU qualifier "Door".
// In case a test module needs to perform diagnostics with different ECUs,
// the function could be called e.g. in the first / initializing test case
// of a test group for each specific ECU

void MainTest ()
{
  if( 0 != diagSetTarget( "Door")) write( "Error setting target!");
  // ... Call your test cases here
}
```
