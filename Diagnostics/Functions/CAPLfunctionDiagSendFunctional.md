[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagSendFunctional.md)

**CAPL Functions** » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » diagSendFunctional

# diagSendFunctional

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
If one or more **Functional Group Request** descriptions are defined at the network, this function does not work. In this case, set the FGR description as target and communicate using the appropriate means.

## Function Syntax

```
long diagSendFunctional( diagRequest request)
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```
diagRequest::SendFunctional()
```

## Description

Send a request to the functional group defined for the current target. The configuration of the functional transport protocol settings in the description configuration dialog must be present and consistent.

**Note**  

- Only responses from the current target are received, responses from other ECUs are ignored.
- The reception channels for ALL ECUs that are member of the same functional group are opened to make sure that they do not run into transport protocol errors. Note that the Tester Present is NOT activated if those channels were not open before! It might be necessary to activate it when a different target is selected.

**Note on Usage with Diagnostics on K-Line**  
When used together with the built-in K-Line diagnostic channel, also the channel will be initialized to use functional addressing i.e. a functional **startCommunication** service will be put on the K-Line (Bit 6 & 7 of format byte set to **1**) when the first request is sent. All subsequent requests sent with this function to the same target ECU will also carry the **use functional addressing** information.

In order to switch back to physical addressing, you have to call [diagCloseChannel](CAPLfunctionDiagCloseChannel.md)(ECU_Qualifier) and then [DiagSetTarget](CAPLfunctionDiagSetTarget.md)(ECU_Qualifier) to prepare the re-opening of the channel upon the next request.

## Parameters

- **request**: The request to be sent.

## Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

```plaintext
on key 'f'
{
  diagRequest Serial_Number_Read req;
  long ret;
  if (0 != (ret=diagSetTarget("ECU1"))) write("diagSetTarget() failed with error code %ld!", ret);
  // Send request on functional channel
  if (0 != (ret=diagSendFunctional(req))) write("diagSendFunctional() failed with error code %ld!", ret);
}

on key 'p'
{
  diagRequest Serial_Number_Read req;
  long ret;
  // reset functional to physical addressing, if necessary
  if (0 != (ret=diagSetTarget("ECU1"))) write("diagSetTarget() failed with error code %ld!", ret);
  // Send request on physical channel
  if (0 != (ret=diagSendRequest(req))) write("diagSendRequest() failed with error code %ld!", ret);
}

on diagResponse Serial_Number_Read
{
  char ser_no[30];
  diagGetParameter(this, "Serial_Number", ser_no, elcount(ser_no));
  write("Response from serial no.: %s",ser_no);
}
```

[_Diag_SendFunctional](CAPLfunctionDiagSendFunctionalCallback.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)