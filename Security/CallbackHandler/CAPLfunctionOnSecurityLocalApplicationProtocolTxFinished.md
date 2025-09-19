[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/CallbackHandler/CAPLfunctionOnSecurityLocalApplicationProtocolTxFinished.md)

## OnSecurityLocalApplicationProtocolTxFinished

[CAPL Functions](../../CAPLfunctions.md) » [Security](../CAPLFunctionsSecurityOverview.md) » OnSecurityLocalApplicationProtocolTxFinished

**Valid for**: CANoe DE • CANoe4SW DE

### Function Syntax

```plaintext
void OnSecurityLocalApplicationProtocolTxFinished(char applicationProtocolName[], long result)
```

### Description

This callback handler is called when the transmission of an application protocol is finished.

As the behavior of application protocols are Security specific you have to refer to the Security Source specific manual to get more information about how they work.

You have to call [SecurityLocalStartControlSimulationNode](../Functions/CAPLfunctionSecurityLocalStartControlSimulationNode.md) before this callback is called.

### Parameters

- **char applicationProtocolUserDefinedId[]**  
  The Id of the application protocol, which can be specified in the Security Manager GUI.

- **long result**  
  A Value of 1 means that the action was successful. A value less than or equal to 0 means error.
  - 1: Success
  - 0: Error, no details
  - -1: PDU could not be transmitted
  - -2: Invalid Broadcast message
  - -3: Invalid Length of the tx data
  - -4: MAC could not be calculated
  - -5: Sequence error
  - -6: Not supported function
  - -10: Security is not usable. Reasons can be: Security Manager version is too old. Tool Version is too old. Security Profile is invalid.

### Return Values

—

### Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
