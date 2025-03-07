[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTGenerateBusloadCtrl.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostGenerateBusloadCtrl

# mostGenerateBusloadCtrl

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This function is available with MOST hardware VN2600, VN2610, VN2640, OptoLyzer G2 3150o, OptoLyzer MOCCA compact 50e, and OptoLyzer MOCCA compact 150c.

## Function Syntax

```plaintext
long mostGenerateBusloadCtrl (long channel, long msgs);
```

## Description

The function sends cyclical messages to the control channel. Use the [mostConfigureBusloadCtrl()](CAPLfunctionMOSTConfigureBusloadCtrl.md) function to specify the send parameters and contents of the message.

**Note for OptoLyzer G2 3150o, OptoLyzer MOCCA compact 50e and OptoLyzer MOCCA compact 150c**  
This function shows no effect if the StressNIC is not set to slave mode. For that purpose use [mostSetStressNodeParameter](CAPLfunctionMOSTSetGetStressNodeParameter.md) function with the proper parameter.

## Parameters

- **channel**: Channel of the connected MOST hardware.
- **pkts**:
  - `0`: Stops the busload generation
  - `>0`: Sends the given number of packets
  - `-1`: Sends continual packets

## Return Values

- `<= 0`: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostGenerateBusloadAsync](CAPLfunctionMOSTGenerateBusloadAsync.md) • [mostGenerateLightError](CAPLfunctionMOSTGenerateLightError.md) • [mostGenerateLockError](CAPLfunctionMOSTGenerateLockError.md) • [mostConfigureBusloadCtrl](CAPLfunctionMOSTConfigureBusloadCtrl.md) • [OnMostStress](../EventProcedures/CAPLfunctionOnMOSTStress.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)