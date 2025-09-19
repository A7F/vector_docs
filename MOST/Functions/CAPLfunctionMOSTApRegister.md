[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTApRegister.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostApRegister

# mostApRegister

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long mostApRegister(long fblockID, long instIDDefault); // form 1`
- `long mostApRegister(); // form 2`

## Description

The first function registers the CAPL node at the Application Socket as a function block with the specified FBlockID and InstIDDefault. The function is available in the CAPL section `on preStart` and can be applied once per CAPL node only.

The second function re-registers a previously de-registered CAPL node.

Both functions make an entry in the device's [Local FBlockList](../../../CANoeCANalyzer/MOST/MOSTSimulationApplicationSocketLocalFBlockList.md). If an FBlock with the same FBlockID and InstID has already been registered by another CAPL node, the InstID of the function block to be registered is incremented until the combination {FBlockID, InstID} is unique within the simulated device.

As a result of the call of `mostApRegister()`, if the network status is 'ConfigOk', the device's NetBlock reports the new Local FBlockList to the NetworkMaster.

## Parameters

- **fblockID**: Function block identifier to be registered.
- **instdIDDefault**: Default instance identifier. The actual registered InstID can be retrieved with [mostApGetInstID()](CAPLfunctionMOSTApGetInstID.md).

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md).

## Example

—

[mostApUnregister](CAPLfunctionMOSTApUnregister.md) • [mostApIsRegistered](CAPLfunctionMOSTApIsRegistered.md) • [mostApGetInstId](CAPLfunctionMOSTApGetInstID.md) • [mostApGetFBlockId](CAPLfunctionMOSTApGetFBlockID.md) • [OnMostApInstID](../EventProcedures/CAPLfunctionOnMOSTApInstID.md) • [mostApRegisterEx](CAPLfunctionMOSTApRegisterEx.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
